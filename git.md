---
sort: 2
title: Git Cheatsheet
---

<!-- markdownlint-disable MD025 MD026 MD033 MD041 -->
<!-- omit in toc -->
# Git Cheatsheet

![Git](https://img.shields.io/badge/Git-F05033.svg?logo=git&logoColor=white)
[![License EUPL 1.2](https://img.shields.io/badge/License-EUPL--1.2-blue.svg)](LICENSE)
[![Become a sponsor to JV-conseil](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/JV-conseil "Become a sponsor to JV-conseil")
[![Follow JV conseil on StackOverflow](https://img.shields.io/stackexchange/stackoverflow/r/2477854)](https://stackoverflow.com/users/2477854/jv-conseil "Follow JV conseil on StackOverflow")
[![Follow JVconseil on Twitter](https://img.shields.io/twitter/follow/JVconseil.svg?style=social&logo=twitter)](https://twitter.com/JVconseil "Follow JVconseil on Twitter")
[![Follow JVconseil on Mastodon](https://img.shields.io/mastodon/follow/109896584320509054?domain=https%3A%2F%2Ffosstodon.org)](https://fosstodon.org/@JVconseil "Follow JVconseil@fosstodon.org on Mastodon")
[![Follow JV conseil on GitHub](https://img.shields.io/github/followers/JV-conseil?label=JV-conseil&style=social)](https://github.com/JV-conseil "Follow JV-conseil on GitHub")

<!-- omit in toc -->
## Table of Content

- [Clone a specific branch](#clone-a-specific-branch)
- [Force "git pull"](#force-git-pull)
- [Revert to a good commit](#revert-to-a-good-commit)

## Clone a specific branch

```bash
git clone --branch development https://github.com/username/project.git
```

_src :point_right: [theserverside.com](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/How-to-git-clone-a-specific-branch-only)_

## Force "git pull"

```bash
git fetch --all
git reset --hard origin/master
git clean -f -d
git pull
```

_src :point_right: [stackoverflow.com](https://stackoverflow.com/a/5361169/2477854/)_

## Revert to a good commit

```bash
cd {your-git-repo}
git log
git push origin +{good-commit-sha}:master
```

_src :point_right: [stackoverflow.com](https://stackoverflow.com/a/35291514/2477854/)_

<!-- omit in toc -->
## References 📚

- Git Complete [List of all Commands](https://git-scm.com/docs).
- Git Commands [Cheat Sheet PDF](https://dev.to/doabledanny/git-cheat-sheet-50-commands-free-pdf-and-poster-4gcn).
- [GitHub](https://education.github.com/git-cheat-sheet-education.pdf) Git Cheatsheet.
- [GitLab](https://about.gitlab.com/images/press/git-cheat-sheet.pdf) Git Cheatsheet.

<!-- omit in toc -->
## Sponsorship

If this project helps you, you can offer me a cup of coffee ☕️ :-)

[![Become a sponsor to JV-conseil](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/JV-conseil)
