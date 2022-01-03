This folder contains the source used to generate a static site using Nikola.

Installation and documentation at https://getnikola.com/

Configuration file for the site is ``conf.py``.

There are two git branches; the source branch is where changes should
be made (src), and the branch where the HTML will be located (master).

To build the site::

    nikola build

To see it locally::

    nikola serve -b

To deploy changes to github.io::

    nikola github_deploy

Note that this will auto-commit any changes.  It can take up to 20
minutes for deployed changes to be seen at github.io.

To check all available commands::

    nikola help
