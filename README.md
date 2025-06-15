# RSCDS Buffalo Branch Website

This repository contains the source code of the RSCDS Buffalo Branch website. It's a simple static site, made to be legible and accessable to all.

## Maintaining rscdsbuffalo.com

This site is built with [Zola](https://www.getzola.org/), and source controlled with [Git](https://git-scm.com/). These instructions assume a POSIX terminal, e.g. "git bash" on Windows, ZSH on MacOS, BASH or ZSH on Linux, etc.

Install Git and Zola if needed.

Change to the `rscds_buffalo` folder in your terminal.

Fetch & update the `main` branch: `git checkout main && git fetch && git pull --ff-only`.

Create a new branch with `git checkout -b <branch name>`, e.g. `git checkout -b update_schedule_for_2026`.

Edit the Markdown files as desired. Test changes by running `zola serve` and opening [the page it creates](http://127.0.0.1:1111) in your browser. Zola will re-generate the page when you change the Markdown sources.

Commit changes to `git` (e.g. `git commit -a`). Write a descriptive message. Try to have one change per commit, you can "roll back" commits independently if needed, that's harder if they have lots of changes.

Push your changes up to GitHub & make a pull request to `main` from your branch.

## Deploying changes

Tag the commit you want to deploy (usually the latest in `main`), and write a summary of the changes since the last release in the message. Push the tag to the origin with `git push <tag name> origin`.

Build the `public_html` directory by running `zola build`.

Log into the site's sFTP server.

Make a `public_html_new` directory on the remote server.

Upload the local `public_html` directory contents into the remote `public_html_new`.

Rename the remote `public_html` to `public_html_old` and rename the remote `public_html_new` to `public_html`. Check that the new site appears as desired by navigating to `https://rscdsbuffalo.com` and clearing cash & refreshing (press Ctrl+F5 to clear cache and refresh). Assuming it's correct, delete the remote `public_html_old` directory.

Log out of the FTP server.
