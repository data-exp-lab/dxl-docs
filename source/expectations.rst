Expectations
============

Authorship
----------

Projects that lab members bring with them **do not** automatically confer
authorship rights to either Matt or other lab members.  However, if work is
conducted on them during the course of being present in the lab,
acknowledgments would be appreciated; funding acknowledgments may be necessary.

Projects that are collaborated on between lab members do confer authorship,
whether that collaboration takes the form of intellectual collaboration or
technical collaboration.  For instance, writing code to support analysis or
simulation would confer authorship.  Sharing information during group meetings
does not, although if material intellectual contributions are made by lab
members, that would confer authorship.  Matt would **very much** to be involved
in the development of projects that lead to publication, but this is not
strictly necessary, and certainly not necessary where lab members are providing
supporting roles to external collaborations.  Please keep Matt apprised of the
broad outlines of your external and internal collaborations.

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


Project Leadership
------------------

When software is developed as a result of funded activity, the leadership
directions will be set collaboratively during the proposal writing process and
then subsequently between lab members and Matt.  For projects which are
externally developed (for instance, ``yt``), leadership for the project as a
whole will be conducted as decided by the broader community.  However, internal
to the lab, development may proceed somewhat in parallel, with the ultimate
goal of conforming to upstream expectations and development strategies.

Decisions regarding strategic direction for software projects (including
algorithmic strategies) will be made collaboratively with Matt and involved lab
members.

For technical directions on lab-developed software, we operate by `"lazy
consensus," <https://rave.apache.org/docs/governance/lazyConsensus.html>`_
which can be conducted via the ``dxl@ncsa.illinois.edu`` mailing list.

For social direction, particularly when engaging with external communities of
researchers about data and data analysis, please keep Matt CC'd on email
communication.

Data Management
---------------

Data Management: When data is utilized by the lab, how is it stored?  How are
files named?  Where would relational databases and their tables be stored?  Is
there a naming convention?  When data is generated, how is it stored?  How is
access to data managed (i.e., is data on a filesystem accessible to all members
of the lab?  Is there an assumption of privacy?)  Is data cataloged, are notes
kept, and how is the cataloging system handled?

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
