Writing Papers
==============

.. note:: A template repository can be found here:
          https://bitbucket.org/data-exp-lab/dxl-paper-template
          and an example of a repository that does a very good job of meeting
          the philosophical guidelines can be seen here:
          https://bitbucket.org/ngoldbaum/galaxy_analysis

From a practical perspective, the process of writing papers will go through
several stages, including conception, drafting, iteration on content and text,
submission, and iteration post-submission.

As noted in :ref:`openness` and :ref:`reproducibility`, there are certain
expectations of openness and inclusion of supplemental materials in the version
controlled repository for a paper.  This section includes supplemental
mechanics for how to write a paper, from the perspective of repository
organization and contents.

The layout of a paper repository should follow this rough organization:::

  /README
  /Makefile
  /ms.tex
  /refs.bib
  /figures/
  /data/
  /scripts/
  /supplemental/

If the paper is particularly long, add a new directory called ``sections`` and
using the ``\input`` directive in LaTeX to include subsections from that
directory.  The names are subject to change (although ``ms.tex`` is preferred)
to meet the needs of individual papers.  Often, ``.bst`` and ``.sty`` files are
included as well.

Below are some guidelines on what to check into the repository; these are
designed to balance the repository size and repository churn against difficulty
of recreating paper components.

These are things that should not be checked into the repository:

 * The generated PDF, until submitted, at which point it should be named
   ``ms_submitted.pdf`` (or something similar) and checked in.
 * The supplemental generated files from LaTeX.  This includes ``.out``,
   ``.log``, ``.aux``, ``.blg``, etc.

Figures Directory
-----------------

The ``figures/`` directory should contain binary files (both ``png`` and
``pdf``) for figures that are difficult to re-create, such as those that are
created from large amounts of data.  Any hand-drawn diagrams should also be
checked in here in whatever raw format is appropriate (for instance, original
Gimp files).

All figures included in the paper should be included directly from this
subdirectory.  All figures generated from the ``scripts/`` directory should
generate into this directory.

When finalizing the paper for submission, *all* figures included in the paper
should be checked into this directory.  Individuals checking out the repository
should be able to generate the paper using just the LaTeX compiler.

Data Directory
--------------

During the course of analysis of data, intermediate data products will be
generated.  Taking as an example analysis of a large set of simulations, there
are two stages to generating a set of plots:

 * Generation of reduced data products from large simulation
 * Generation of plots from that set of reduced data products

The first stage is often the more time consuming in terms of IO and flops, but
the second is where many particular steps of tweaking fonts, symbols,
linestyles, etc, occur, and while likely less consuming in total time, it is a
step that is repeated.

Placing the results from the first step of the process into the ``data/``
directory allows the two steps to be separated, and reduces the need to
constantly re-run analysis in order to make minor aesthetic changes.  Some
things that might be reasonably stored include 1D data series extracted from
larger datasets, data buffers for plots (i.e., the output of a
``FixedResolutionBuffer`` from yt), data points for scatter plots corresponding
to larger datasets that have been dimensionally reduced, etc.

Data products stored in this directory should follow these guidelines:

 * Be the minimum amount of data necessary
 * Use a non-Pickle data format.  HDF5 is *strongly* preferred, but CSV and
   JSON are also acceptable.  Pickle is unacceptable, as is raw binary.
 * They should be as self-describing as possible.  Metadata should be stored
   either in the data file or in a sidecar file sharing the same name and a
   supplemental ``.info`` extension.

Scripts Directory
-----------------

This directory should include all scripts used to generate reduced data
products (whether or not it is stored in the ``data/`` directory), all scripts
used to generate plots (*no* plots should be bespoke, hand-generated), and all
scripts used to combine or explore data.

All scripts should be expected to be run from the root directory of the
repository, and should generate into either ``data/`` or ``figures/``.  These
scripts should make a best effort to identify their dependencies and required
version numbers.

An alternate approach that is more robust, particularly against dependency
information and installation issues, is to develop a ``setup.py`` file in the
``scripts/`` repository that transforms it into an installable, editable
package.  See the ``ngoldbaum`` example paper repository, linked above, for how
this might work.  This helps identify dependencies through ``install_requires``
as well.
