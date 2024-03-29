########
XRef RST
########

This package provides a reStructuredText back-end for Emacs ``Xref``.

This means you can look-up links at the cursor as well as finding references to link-targets.

Available via `melpa <https://melpa.org/#/xref-rst>`__.


Motivation
==========

For large multi-file projects, being able to jump to links can be useful.


Usage
=====

Once enabled, the following ``Xref`` functions can be used with RST files.

``xref-find-definitions``
   Look up the symbol at the cursor.

   Supports ``ref``, ``term``, ``doc`` and file-paths (in an ``index`` for example).
``xref-find-references``
   Shows references to a target when the cursor is over one.

   Supports ``ref`` targets and terms in the ``glossary``.


This can be enabled using ``xref-rst-mode`` (a buffer-local minor-mode), for example:

.. code-block:: elisp

   (add-hook 'rst-mode-hook #'xref-rst-mode)


Customization
-------------

``rst-find-in-project-extensions`` (``'(".rst" ".txt")``)
   A list of literal file extensions to search.


Details
=======

- The projects root is detected by searching for ``conf.py`` (used by Sphinx),
  otherwise version control is used to find the root.

- Files and directories beginning with a ``.`` are ignored.

- The ``xref-rst-mode`` minor mode simply handles adding/removing the ``Xref`` back-end.
