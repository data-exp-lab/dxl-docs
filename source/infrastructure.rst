Infrastructure Guide
====================

Compute Resources
-----------------

We have five dedicated use nodes available.  These nodes are not currently
provisioned through the NCSA Nebula system (http://nebula.ncsa.illinois.edu)
but will be soon.  They will typically be pre-provisioned to allow for
individual systems to be utilized by users.  At present, two of the five nodes
are online.

These nodes have 20 cores each allowing 2 threads per core for a total of 40
compute cores and are configured with 256GB of RAM.  The storage available on
them is networked in ``/dpool/`` and each user will have their own directory in
``/dpool/``.

These nodes are configured such that each user that logs in will be logged into
a `Docker <http://docker.com>`_ container.  This is accomplished by providing
an ssh key to Kacper, and he will return to you the correct port to use to log
in.  This will then require you to log in to that specific port:::

  ssh -p 31425 dxl1.ncsa.illinois.edu

where the port, here `31425`, will be specific to your username.  You can set a
shorthand for this in `~/.ssh/config` like this:::

   Host dxl1
     IdentityFile ~/.ssh/ssh_key_dxl
     Port 31425

Replace the values with the key you utilize and the port you are provided.

Additionally, you may be able to provision nodes directly through the Nebula
interface.

NCSA has an allocation on the Illinois Campus Cluster
(https://campuscluster.illinois.edu/ ) which you may utilize for further
computing needs.  To gain access, request a new user listing Matt as the
contact and request the NCSA queue.

In addition, we also have an Oculus Rift, two Google Cardboards, a Leap Motion,
and a few Chromecast devices.

Shared Storage
--------------

On the dxl nodes, we have roughly 500TB of storage space that is shared in the
``/dpool/`` directory structure.  Please utilize this wisely, and consider it
to be a shared resource amongst the lab.

Version Control
---------------

The preferred version control system for DXL projects is `Mercurial
<http://mercurial-scm.org/>`_ although in some specific cases Git can be
utilized.  At present, we utilize BitBucket under the ``data-exp-lab`` team.
Our list of repositories is available at http://bitbucket.org/data-exp-lab/ .

A good guideline for version control is to version control any piece of code
that rises above the level of a simple script for testing external software.
Projects that directly relate to lab work should be stored under the lab
team account.  Pre-existing and external projects should reside in their
original locations, and not all software projects are "lab" projects.

Accounts
--------

Lab members will have the following accounts:

 * NCSA account, which will provide access to most resources
 * UIUC account, which will be used for Campus Cluster.
 * Various accounts related to external providers: `BitBucket
   <http://bitbucket.org/>`_, `Trello <http://trello.com/>`_, and Slack
   (invitation will be issued).

Tools
-----

This section will be filled out over time, but it will include links to
software and hardware tools that may be of use.

We run several services.

 * curldrop: You can execute ``curl -T somefile http://use.yt/upload/`` to
   share a file up to several gigabytes.  The return value will be the hash at
   which the file can be located.
 * ownCloud: You can log in with your NCSA credentials to
   https://hub.yt/owncloud/ to access a private ownCloud instance, which acts
   like Dropbox or Google Drive.  Currently this has a total of 4TB available,
   but may be migrated to using ``/dpool/`` eventually. This resource can also
   be mounted locally, provided that you have `davfs2
   <http://savannah.nongnu.org/projects/davfs2>`_ installed
   
   .. code-block:: console

    mkdir owncloud
    sudo mount -t davfs \
       https://hub.yt/owncloud/remote.php/webdav \
       $PWD/owncloud
   ..

   For convienience it is possible to modify ``/etc/fstab`` and set a permanent
   mountpoint. Additional details can be found in `OwnCloud's manual
   <https://doc.owncloud.org/server/7.0/user_manual/files/files.html>`_.
 * You can start a new `SAGE2 <http://sage2.sagecommons.org/>`_ instance by
   visiting http://use.yt/startsage/ . This will return you both a hash you
   can share with others (for screen sharing) and a running instance of SAGE2.
 * Hackpad: we are exploring running a hackpad instance.
 * The yt pastebin at http://paste.yt-project.org/ is hosted on DXL resources
   and can be accessed via the command line through the ``yt`` command line
   tool and the ``pastebin`` and ``pastebin_grab`` subcommands.
 * public jupyterhub: Anyone with BitBucket account can spawn a jupyter 
   server with access to example datasets and yt quickstart. Service is
   available at https://use.yt/
 * private jupyterhub: DXL members can spawn jupyter server that automounts
   their owncloud home directory and has access to dxl's storage pool using
   their NCSA's credentials. Service is available at https://hub.yt/jupyter-dev/
   
The `dxl-tools <http://bitbucket.org/data-exp-lab/dxl-tools>`_ repository
includes tools to utilize our curlDrop server and to connect to remote Jupyter
kernels on dxl resources.  Until it is released on PyPI, you can install it
manually or with ``pip install
hg+http://bitbucket.org/data-exp-lab/dxl-tools`` .  To use it, you must create
``~/.dxl/dxl.cfg`` and put in it:::

   [dxl]
   upload_url = http://use.yt/upload/

You can then upload files with:::

   dxl upload file1 file2 file3

Purchasing
----------

To purchase equipment, whether that is computer hardware/accessories or
intellectual materials such as books, send an email to Matt's Illinois address
with links to the equipment on `CDW <http://cdw.com/>`_, `Dell
<http://dell.com/>`_ or `Amazon <http://amazon.com/>`_ along with prices and a
sentence or two about what they are and why you need the items.  He will
forward it on to the appropriate contact people.
