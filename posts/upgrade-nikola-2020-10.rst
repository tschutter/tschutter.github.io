.. title: Upgrade Nikola (2020-10)
.. slug: upgrade-nikola-2020-10
.. date: 2020-10-23 16:16:35-06:00
.. tags: nikola
.. category:
.. link:
.. description:
.. type: text

Installation Changed
--------------------

When I first installed Nikola a year ago, I just used pip3 to install
the Nikola package.  That version of Nikola broke when Python was
upgraded from 3.7 to 3.8.  The current recommended procedure is to
install Nikola in a virtual environment.

Update Procedure
----------------

1. Install python3-venv on Ubuntu::

     sudo apt-get install python3-venv

2. Create a venv called "nikola"::

     cd ~/src/tschutter.github.io
     python3 -m venv nikola

3. Add nikola dir to the ``.gitignore`` file::

     grep -qxF 'nikola' .gitignore ||\
       echo "$(echo nikola | cat - .gitignore | sort)" > .gitignore
     git commit -m ".gitignore: added nikola venv" .gitignore

4. Enable the new venv::

     cd nikola
     source bin/activate

5. Upgrade pip, setuptools, and wheel modules in the venv::

     bin/python -m pip install --upgrade pip setuptools wheel

6. Install Nikola::

     bin/python -m pip install --upgrade "Nikola[extras]"

7. Disable old version of Nikola::

     sudo mv /usr/local/bin/nikola /usr/local/bin/nikola-old
     cd /usr/local/lib/python3.7/dist-packages
     sudo mv nikola nikola-old
     sudo mv Nikola-8.0.2.dist-info Nikola-old-8.0.2.dist-info

See also:

- `Nikola -> Getting Started <https://getnikola.com/getting-started.html>`_
- `Python Virtual Environments in Five Minutes
  <https://chriswarrick.com/blog/2018/09/04/python-virtual-environments/>`_
- `venv — Creation of virtual environments
  <https://docs.python.org/3/library/venv.html>`_
