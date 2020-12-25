F&S Book
********

Sphinx assets
==============

::

	_build/
	build/
	source/
	Makefile

Install and run
===============

::

    $ python -m venv .venv
    $ source .venv/bin/activate
    $ pip install -r requirements.txt

Build the Guide::

    $ make html

or ::

    $ sphinx-build source build -b html 

Open the Guide::

    $ google-chrome-stable build/html/index.html

Install `dev-requirements.txt` using `pipm
<https://github.com/jnoortheen/pipm>`__ ::

    $ pipm install --dev

and start Live Preview::

    $ sphinx-reload .

i18n
====

`sphinx-intl <https://www.sphinx-doc.org/en/master/usage/advanced/intl.html>`__

Make *.pot files (just once, at the start of the i18n):

::

    $ make gettext

Generate *.po files (just once):

::

    $ sphinx-intl update -p build/gettext -l ru

Build:

::

    $ make -e SPHINXOPTS="-D language='ru'" html
