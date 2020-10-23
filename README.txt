This folder contains the source used to generate a static site using Nikola.

Installation and documentation at https://getnikola.com/

Configuration file for the site is ``conf.py``.

To build the site::

    nikola build

To see it locally::

    nikola serve -b

To deploy changes to github.io::

    nikola github_deploy

Note that it can take up to 20 minutes for deployed changes to be seen
at github.io.

To check all available commands::

    nikola help
