Expectations
============

Authorship
----------

Projects that lab members bring with them **do not** automatically confer
authorship rights to either Matt or other lab members.  However, if work is
conducted on them during the course of being present in the lab,
acknowledgments would be appreciated; funding acknowledgments may be necessary.

Projects that are collaborated on between lab members do confer authorship,
whether that collaboration takes the form of intellectual collaboration,
technical collaboration or data sharing.  For instance, writing code to support
analysis or simulation would confer authorship.  Sharing information during
group meetings does not, although if material intellectual contributions (i.e.,
new directions, solutions to problems, specific and directed project ideas) are
made by lab members, that would confer authorship.

Matt would **very much** to be involved in the development of projects that
lead to publication, but this is not strictly necessary, and certainly not
necessary where lab members are providing supporting roles to external
collaborations.  Please keep Matt apprised of the broad outlines of your
external and internal collaborations.

Project Ownership
-----------------

From a social, rather than a licensing or intellectual property perspective,
when a project is developed in the lab primarily by a single participant, that
participant is free to continue developing and assuming project leadership once
they have departed the lab.  In fact, developing projects that mature, grow,
and may contribute to their future career is a key part of the process of
scientific development.

For projects that are collaboratively developed with multiple roughly equal
participants, "leadership" will be decided on a case-by-case basis, erring on
the side of providing intellectual freedom and empowerment to earlier-stage
researchers.

However, projects that are part of a strategic lab direction may continue to be
developed within the lab following departure of a primary developer.  In such a
case, decisions about "forking" or bifurcating development will be held on a
case-by-case basis.

Lab Presence and Environment
----------------------------

.. note::

   Human resources guidelines take precedence over this section.

Full-time lab members are encouraged to make themselves available during normal
working business hours, although this is a flexible definition; in general, if
you are able to come to the office between 10-4, that is desirable.  Remote
lab members should try to be available during those hours and accessible
online or via phone.  We intend to foster a collegial lab atmosphere, with
opportunities for spontaneous discussions and creative opportunities.

Lab members are *not* expected to sacrifice personal or leisure time in service
of projects.  Working long hours without interruption can lead to burnout,
exhaustion, and overall *impedes* the type of atmosphere we are trying to
develop.

Lab members are encouraged to participate in NCSA activities as well as
activities in other departments on campus (Astronomy, GSLIS, Beckman,
Informatics).  This includes contributing to NCSA projects, collaborating with
individuals from other groups around campus and the center, and fostering new
collaborations both internal and external to UIUC.  We strive to be a part of
the intellectual community at NCSA and UIUC.  Lab members should endeavor to be
good "citizens" at NCSA, participating in colloquia, all-hands meetings, and
other projects as they become available.

Data Management
---------------

When data is used by the lab, it is expected to reside on the shared
filesystem.  Accompanying this should be an index or README file describing
what the data *is*, where it originated from, and what restrictions there are
on its use.  When data is stored on the shared filesystem, there is no
expectation of privacy within the lab unless it is explicitly enforced; for
special cases this can be dealt with differently.  Lab members are not
encouraged to browse other directories, but it is not forbidden.  For example,
this might be an example directory structure:::

  /dpool/mturk/DarkSkySims-DS14a/README
  /dpool/mturk/DarkSkySims-DS14a/ds14_a_1.0000.sdf
  /dpool/mturk/LIDAR-Philly/README
  /dpool/mturk/LIDAR-Philly/data*
  /dpool/mturk/HRRR-20140726/README
  /dpool/mturk/HRRR-20140726/dir1/*
  /dpool/mturk/HRRR-20140726/dir2/*

and so on.  In the near-term future, we will be deploying a data cataloging
system which will be fed with the data from README files, and which will be the
primary cataloging system in the future.

Wherever possible, names should conform to including either a date (if the data
is tied to a specific time, parameter query or observation) or a
semantically-meaningful name (if it is part of a larger project.)

Openness
--------

Unless there is a *very* good reason (PII or other restrictions, for instance),
work should be conducted in public repositories on publicly accessible servers
such as bitbucket.  This includes software.  Paper repositories should be open,
but may be held back as private until time of either first submission to a
journal, a preprint server, *or* a non-author for review.  Because it is
expected that repositories will be made publicly accessible, including history
of changesets, lab members are encouraged to behave professionally in them.

.. note::

   Many professional societies, including AAS, consider the content of referee
   reports to be *de facto* confidential.  As such, unless the report is
   explicitly open, it should not be added to repositories as text, commit
   messages, or comments in papers.

Grant proposals developed internally with no external PIs or Co-PIs should be
made available unless there is confidential information.  Grant proposals
developed in collaboration with external PIs or Co-PIs may be kept
confidential at the external collaborators discretion, although our preference
is for them to be open.

Record Keeping
--------------

Lab members are expected to keep notes of their actions.  This can be somewhat
free-form, as the purpose is not to keep "tabs" on actions, but instead to
ensure that work can be reconstructed.  These can be kept either in a
centralized lab repository, next to specific projects in text files, or on
Trello cards on the DXL organization.

Reproducibility
---------------

Unless strongly prohibited by external concerns, the necessary components of a
scholarly work to provide reproducibility should be provided in a publicly
accessible location and potentially as part of the scientific record.  In the
case of an astrophysical simulation paper, this would include:

 * The source code that ran the simulation (shorthand would be the hash of the
   publicly available source)
 * The parameter file or definitions file, and if applicable initial
   conditions, that ran the simulation.
 * Analysis code that generated plots from the paper.

The overall theme here is that of reproducibility; this is not the same as
bitwise identical reproduction, which is often unavailable because of
constraints such as order-of-arrival differences.  The additional overhead of
making work reproducible should not be onerous compared to the other
expectations, and in many ways (i.e., turnkey plot generation, good note taking
on data, etc) can reduce the overall effort of developing papers and workflows.

We will endeavor to respond to requests to reproduce DXL results by providing
necessary technology and data, allowing for reasonable commitments of time and
effort.

Ethics
------

Note: this is distinct from the code of conduct for the lab, which applies both
within and without the lab.

Our actions should be guided by the ethics of participating in the scientific
community.  This includes prioritizing our professional obligations over fear
of being "scooped."  For instance, it is *completely unacceptable* to interfere
with the peer review process for a paper out of concern of protecting one's own
work (i.e., "sitting" on a review for it, making unreasonable requests to delay
publication, and so on.)

When competitors request assistance with software developed in the lab, we
should attempt to make a best effort to assist them.  It is not unreasonable to
ask for authorship, particularly if the collaboration is extensive.

When authoring papers, we should be providing citations to all software that
assisted in the development of the scholarly work.  While in the extreme case
this would extend to the operating system level, in general it is acceptable to
cite the layers of software in the analysis stack (e.g., NumPy, Matplotlib,
IPython/Jupyter, SymPy, yt, etc.)  It is preferred to directly cite the
canonical papers (often described in ``CITATION.txt`` files) for software, but
acknowledging them without citation may be sufficient.

Citations to data DOIs or publications should be made wherever possible, and
where not possible, should be included as footnotes.

When developing software, we must make a best effort to cite which pieces of
software contributed to the development.

Plagarism is unacceptable in any form.  This includes "first pass" text
included in papers or proposals; when "first pass" text is included from an
external source, it must be clearly marked as such to ensure it is not
accidentally included in the final product.

Acknowledgments
---------------

If you are supported by the Moore Foundation, please include this text in your
paper's acknowledgments section:

   This publication is supported in part by the Gordon and Betty Moore
   Foundation's Data-Driven Discovery Initiative through Grant GBMF4561 to
   Matthew Turk.

If you are supported by the NSF SI2 award, please include this text in your
paper's acknowledgments section (see `Section 3
<http://www.nsf.gov/pubs/gpg/nsf04_23/6.jsp>`_)

   This material is based upon work supported by the National Science
   Foundation under Grant No. ACI-1535651.

Except for articles or papers published in scientific, technical or
professional journals, the following disclaimer must be included:

   Any opinions, findings, and conclusions or recommendations expressed in this
   material are those of the author(s) and do not necessarily reflect the views
   of the National Science Foundation.

At present, all postdocs in the lab are supported at least in part by both
awards.
