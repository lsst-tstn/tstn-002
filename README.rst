.. image:: https://img.shields.io/badge/tstn--002-lsst.io-brightgreen.svg
   :target: https://tstn-002.lsst.io
.. image:: https://github.com/lsst-tstn/tstn-002/workflows/CI/badge.svg
   :target: https://github.com/lsst-tstn/tstn-002/actions/

############################
Software Deployment Strategy
############################

TSTN-002
========

This document describes the software deployment strategy to be implemented by T\&S.
It contains a definition and list of the software products that will be delivered by T\&S and the
path from development and maintenance to deployment. Software provided by external
vendors will be incorporated to the process in due time. It is also recommended that
software provided by other subsystems follows the procedures established by this document.

Links
=====

- Live drafts: https://tstn-002.lsst.io
- GitHub: https://github.com/lsst-tstn/tstn-002

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-tstn/tstn-002

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the `acronyms.tex` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
