===========
homepage.py
===========

------------------
homepage generator
------------------

:Author: Ondrej Kipila <ok100 at openmailbox dot org>
:Version: git
:Manual section: 1

SYNOPSIS
========

``homepage.py [-h] [-c file] [-o directory]``

DESCRIPTION
===========

homepage.py is a basic homepage generator.

OPTIONS
=======
``-h``, ``--help``
    Show help message and exit.
``-c``, ``--config-file file``
    Change the configuration file of homepage.py from default ``$HOME/.config/homepage/homepage.conf`` to ``file``.
``-o``, ``--output-dir directory``
    Change the output directory of homepage.py from default ``$HOME`` to ``directory``. Two files will be created in this directory: ``homepage.html`` and ``style.css``.

CONFIGURATION OPTIONS
=====================

Default path to the configuration file is ``$HOME/.config/homepage/homepage.conf``.

Configuration file with default options would look like this::

    import os
    from collections import OrderedDict
    
    output_dir = os.environ['HOME']
    title = 'Speed Dial'
    font = ('Monospace', '12pt')
    separator = '>'
    colors = (
        '#020202',  # background
        '#999999',  # links
        '#B3B3B3',  # group title
        '#4C4C4C',  # separator
    )
    links = OrderedDict([
        ('search', [
            ['google', 'https://www.google.com/'],
            ['duckduckgo', 'http://duckduckgo.com/'],
            ['startpage', 'https://startpage.com/'],
        ]),
        ('media', [
            ['youtube', 'http://www.youtube.com/'],
        ]),
        ('foo', [
            ['wikipedia', 'http://en.wikipedia.org/wiki/Main_Page'],
            ['wallbase', 'http://wallbase.cc/home'],
        ])
    ])

Options
-------

``output_dir`` (type: ``string``)
    Output directory.

``title`` (type: ``string``)
    Page title.

``font`` (type: ``tuple``)
    Font. First element is font name (``string``), second element is font size (``string``).

``separator`` (type: ``string``)
    Separator between group title and links.

``colors`` (type: ``tuple``)
    Colors. Consists of four ``string`` elements: background, links, group title, separator.

``links`` (type: ``OrderedDict``)
    Links (see example configuration file above).
