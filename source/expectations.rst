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

Grant proposals should be made available unless there is confidential
information.

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
constraints such as order-of-arrival differences.

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
IPython/Jupyter, SymPy, yt, etc.)

Citations to data DOIs or publications should be made wherever possible, and
where not possible, should be included as footnotes.

When developing software, we must make a best effort to cite which pieces of
software contributed to the development.
