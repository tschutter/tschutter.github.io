.. title: Setup Nikola
.. slug: setup-nikola
.. date: 2019-09-15 17:57:42-06:00
.. tags: nikola
.. category:
.. link:
.. description:
.. type: text

Setup Procedure
---------------

1. Install Nikola::

    pip install --upgrade "Nikola[extras]"

2. Initialize the user site::

    nikola init --demo ~/src/tschutter.github.io

3. Create a tschutter.github.io repository on GitHub.

4. Connect the local repository to the GitHub repository::

    cd ~/src/tschutter.github.io
    git init
    git remote add origin git@github.com:tschutter/tschutter.github.io.git

5. Create a .gitignore file::

      cache
      .doit.db*
      __pycache__
      output
      .ipynb_checkpoints
      .DS_Store

6. Commit initial files::

    git checkout -b src
    git add .
    git commit -m "initial checkin"
    git push -u origin master

7. Edit conf.py.

8. Deploy to tschutter.github.io::

    nikola github_deploy

See: :doc:`Nikola Static Site Generator <nikola-static-site-generator>`
