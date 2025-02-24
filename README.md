# release testing

The workflow here shows how one could have a new release trigger a workflow
which then does some automatic updates (here signified by updating `version`)
and then pushing these auto updates in a new commit to `main` and updating the
tag of that release to this new commit on main.

This workflow **will fail** if the default branch is protected from pushes
(either the no-force-pushes rule or the requirement of a PR rule).
One could update their branch protection rules to allow the bot actor to bypass
the rules, but that then opens up someone (intentionally or maliciously) using
the workflow to forcibly change the code on `main`.
