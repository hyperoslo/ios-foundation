# Working on open source projects with your own fork

This document aims to simplify the process of setting up a workflow where you only push changes to your own fork of open source projects. The idea is that each developer makes a fork of all the open source projects that we work on, and then uses the PR workflow to submit changes.

Steps to get setup:

1. Fork the project you'll be working on to your own GitHub account
2. Clone the project (if you haven't done so already)
3. Modify the push URL of the `origin` in your local clone: `$ git remote set-url --push origin <Git URL to your fork>`
4. You can now `git pull` from the master repo, and `git push` to your fork :tada:
5. If you need to also pull from your fork, you can add it as a separate remote: `git remote add fork <Git URL to your fork>`
