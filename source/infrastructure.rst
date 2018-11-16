Infrastructure Guide
====================

Compute Resources
-----------------

We have two nodes not provisioned through the NCSA nebula system, and we have a
quota for a sizable set of Nebula resources (http://nebula.ncsa.illinois.edu)
that are available for our use.

The two non-provisioned nodes (dxl1 and dxl2 at ncsa.illinois.edu) have 20
cores each allowing 2 threads per core for a total of 40 compute cores and are
configured with 256GB of RAM.  The storage available on them is networked in
``/dpool/`` and each user will have their own directory in ``/dpool/``.

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

Matt has a Blue Waters allocation you can be added to for judicious use of
resources at that scale.

Hardware
--------

We have a few things that you can use varying in degrees of playfulness and
utility.

 * HTC Vive
 * Two Oculus Rift consumer products, one development kit (with Oculus
   Touch controllers)
 * `Project Tango tablet <https://en.wikipedia.org/wiki/Tango_(platform)>`_
 * Chromecast
 * Dell android tablet
 * `Dark Side lego kit
   <https://lego.fandom.com/wiki/9754_Dark_Side_Developer_Kit>`_
 * Google Cardboard (including `View Master
   <https://www.greenbot.com/article/2995583/android/the-best-cheap-cardboard-vr-viewer-is-mattels-view-master.html>`_)
 * Leap Motion
 * USB controller (works with `ipywidgets
   <https://ipywidgets.readthedocs.io>`_)

Version Control
---------------

The preferred version control system for DXL projects was `Mercurial
<http://mercurial-scm.org/>`_ but as a result of project transitions, we
primarily now use Git and Github.

We have homes on both GitHub and Bitbucket:

  * https://github.com/data-exp-lab/
  * https://bitbucket.org/data-exp-lab/

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
 * Various accounts related to external providers: `Github
   <https://github.com/>`_, `BitBucket
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
 * Box: University of Illinois has a Box subscription that provides
   quote-unquote unlimited storage.  You can 
 * Hackpad: You can either use `HackMD <https://hackmd.io/>`_ or our
   self-hosted `CodiMD <https://hackmd.hub.yt/>`_.
 * The yt pastebin at http://paste.yt-project.org/ is hosted on DXL resources
   and can be accessed via the command line through the ``yt`` command line
   tool and the ``pastebin`` and ``pastebin_grab`` subcommands.
   
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

The ``dxl`` utility can also upload to Slack.  To use that aspect, go to `Slack
Web API <https://api.slack.com/web>`_ site, and generate an API key for
yourself.  Put that in ``~/.dxl/dxl.cfg`` like so:::

   [dxl]
   slack_api_key=WHATEVER

Now you can use the command:::

   dxl slack_upload file1

Optionally, you can specify ``--channel`` to send it to a specific channel.  To
send to a specific person, you have to specify ``@`` at the start, i.e.,
``--channel "@matt"`` .

Purchasing
----------

To purchase equipment, whether that is computer hardware/accessories or
intellectual materials such as books, send an email to Matt's Illinois address
with links to the equipment on `CDW <http://cdw.com/>`_, `Dell
<http://dell.com/>`_ or `Amazon <http://amazon.com/>`_ along with prices and a
sentence or two about what they are and why you need the items.  If the
purchase is okay, he will forward it on to the appropriate contact people.
