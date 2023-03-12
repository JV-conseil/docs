---
sort: 2
title: Git Cheatsheet
---

<!-- markdownlint-disable MD025 MD026 MD033 MD041 -->
<!-- omit in toc -->
# Git Cheatsheet

[![License EUPL 1.2](https://img.shields.io/badge/License-EUPL--1.2-blue.svg)](LICENSE)
[![Become a sponsor to JV-conseil](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/JV-conseil "Become a sponsor to JV-conseil")
[![Follow JV conseil on StackOverflow](https://img.shields.io/stackexchange/stackoverflow/r/2477854)](https://stackoverflow.com/users/2477854/jv-conseil "Follow JV conseil on StackOverflow")
[![Follow JVconseil on Twitter](https://img.shields.io/twitter/follow/JVconseil.svg?style=social&logo=twitter)](https://twitter.com/JVconseil "Follow JVconseil on Twitter")
[![Follow JVconseil on Mastodon](https://img.shields.io/mastodon/follow/109896584320509054?domain=https%3A%2F%2Ffosstodon.org)](https://fosstodon.org/@JVconseil "Follow JVconseil@fosstodon.org on Mastodon")
[![Follow JV conseil on GitHub](https://img.shields.io/github/followers/JV-conseil?label=JV-conseil&style=social)](https://github.com/JV-conseil "Follow JV-conseil on GitHub")

## How to revert to a good commit

```bash
cd <your-git-repo>
git log
git push origin +<good-commit-sha>:master
```

*src: <https://stackoverflow.com/a/35291514/2477854/>.*

## References 📚

- <https://dev.to/doabledanny/git-cheat-sheet-50-commands-free-pdf-and-poster-4gcn?signin=true>.
- <https://education.github.com/git-cheat-sheet-education.pdf>.
- <https://about.gitlab.com/images/press/git-cheat-sheet.pdf>.
