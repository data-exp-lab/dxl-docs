Coding and Software
===================

Coding Standards
----------------

Code should avoid being "too clever."  This means things like avoiding clever
abuses of language (for instance, utilizing lack of closures in python to
remove the need for a variable) and algorithms that cut corners in the interest
of marginal time savings.

In general, we want to balance all needs for performance with needs for clarity
and maintainability.  Maintainability is the key functionality we need to
emphasize, as this will ensure the code can remain useful beyond the original
scope of the project.

Tests should be considered mandatory for new functionality *and* bug fixes to
lab software.  These tests should be part of automated testing suites.

For Python code, we follow PEP-8 as best as possible.  The yt coding standard
in yt's ``doc/coding_styleguide.txt`` is another good set of guidelines.

Documentation must be added with any new set of code, and should be documented
in a way that is accessible to newcomers to a given project.  Where possible,
worked examples should be provided.

Commenting
----------

Comments should be considered encouraged, but not necessary.  Code should be as
self-describing as possible; where complex optimizations are present, comments
should enable an individual to understand shortcuts and so on.  In particular,
memory-management beyond standard ``free`` and ``malloc`` in C code should be
commented (i.e., ``realloc`` or ``memcpy``) to ensure it is readable and
understood, as memory errors are a significant source of difficulty for many
coding problems.

Whenever possible, citations to algorithms (whether from papers or URLs such as
Stack Overflow) should be included in comments close to that section of the
code.

Whenever developing in Python, docstrings should be added to *all* public
facing functions.  These must at a minimum cover all parameters and expected
output, along with a description of the function.  For an example of a detailed
template docstring format, see the yt codebase in
``doc/docstring_example.txt``.

Licensing
---------

All code generated in the lab should be permissively, non-copyleft Open Source.
If contributions to upstream copyleft projects are made, those contributions
can be licensed in accordance with the upstream project license (i.e.,
contributions to Mercurial can be GPL2+).

Importantly, in the lab we should cultivate an atmosphere of respect for
licensing terms and ensuring that we are at all times in compliance with those
terms.  Our preferred license is BSD 3-clause.

Languages
---------

Typically, there are three categories of code that we encounter: code used for
library-level software, code that requires inner-loops over arrays and so on,
and code that is used to generate user interfaces.

 * General software development: In general, DXL utilizes Python for most of
   its software.  This can include web apps as well as analysis and
   visualization software like yt.  Experimenting with Julia and other
   languages is of course acceptable and even desirable.
 * Fast, optimized code: For this, the first preference is Cython, then C, then
   C++.  Utilizing C++ can sometimes present difficulties for static linking
   and embedded systems.
 * UI code: For any web apps, we utilize Javascript on the frontend with
   appropriate web frameworks; in the past we've used AngularJS, but React/Flux
   and other frameworks are acceptable.  In general, for UI code, following
   industry is a good idea, as is following industry standards for managing
   dependencies and so on (bower, grunt, gulp, etc).

Using Other Code
----------------

In general, using external code in lab projects is a balance between a few
factors.  If a large external project provides a small amount of functionality
that would be used in a lab project which is to be distributed widely, the
difficulty of the external library to install and keep up with (i.e., API
changes) must be accounted for versus the difficulty of either "vendoring" the
functionality (license-permitting) or re-implementing.  In general we want to
utilize external code for functions that are either core functionality of our
projects (numpy, lapack, etc) and for difficulty but non-core functions of our
projects.

If the dependency is a small, lightweight dependency, typically it's better to
utilize it than to re-implement the functionality.  But, for
difficult-to-install libraries or libraries where utilized functionality
outweighs the overhead of installation, it's better to bring it up for a
discussion.
