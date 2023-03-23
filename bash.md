---
sort: 3
title: Bash
---

<!-- markdownlint-disable MD025 MD026 MD033 MD041 -->

<a href="https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html" target="_blank" title="Bourne-Again SHell"><img src="https://bashlogo.com/img/logo/svg/full_colored_dark.svg" align="right" alt="Bourne-Again SHell" height="150"></a>

<!-- omit in toc -->
# Bash

[![made-with-bash](https://img.shields.io/badge/-Made%20with%20Bash-1f425f.svg?logo=image%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyZpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw%2FeHBhY2tldCBiZWdpbj0i77u%2FIiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8%2BIDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuNi1jMTExIDc5LjE1ODMyNSwgMjAxNS8wOS8xMC0wMToxMDoyMCAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENDIDIwMTUgKFdpbmRvd3MpIiB4bXBNTTpJbnN0YW5jZUlEPSJ4bXAuaWlkOkE3MDg2QTAyQUZCMzExRTVBMkQxRDMzMkJDMUQ4RDk3IiB4bXBNTTpEb2N1bWVudElEPSJ4bXAuZGlkOkE3MDg2QTAzQUZCMzExRTVBMkQxRDMzMkJDMUQ4RDk3Ij4gPHhtcE1NOkRlcml2ZWRGcm9tIHN0UmVmOmluc3RhbmNlSUQ9InhtcC5paWQ6QTcwODZBMDBBRkIzMTFFNUEyRDFEMzMyQkMxRDhEOTciIHN0UmVmOmRvY3VtZW50SUQ9InhtcC5kaWQ6QTcwODZBMDFBRkIzMTFFNUEyRDFEMzMyQkMxRDhEOTciLz4gPC9yZGY6RGVzY3JpcHRpb24%2BIDwvcmRmOlJERj4gPC94OnhtcG1ldGE%2BIDw%2FeHBhY2tldCBlbmQ9InIiPz6lm45hAAADkklEQVR42qyVa0yTVxzGn7d9Wy03MS2ii8s%2BeokYNQSVhCzOjXZOFNF4jx%2BMRmPUMEUEqVG36jo2thizLSQSMd4N8ZoQ8RKjJtooaCpK6ZoCtRXKpRempbTv5ey83bhkAUphz8fznvP8znn%2B%2F3NeEEJgNBoRRSmz0ub%2FfuxEacBg%2FDmYtiCjgo5NG2mBXq%2BH5I1ogMRk9Zbd%2BQU2e1ML6VPLOyf5tvBQ8yT1lG10imxsABm7SLs898GTpyYynEzP60hO3trHDKvMigUwdeaceacqzp7nOI4n0SSIIjl36ao4Z356OV07fSQAk6xJ3XGg%2BLCr1d1OYlVHp4eUHPnerU79ZA%2F1kuv1JQMAg%2BE4O2P23EumF3VkvHprsZKMzKwbRUXFEyTvSIEmTVbrysp%2BWr8wfQHGK6WChVa3bKUmdWou%2BjpArdGkzZ41c1zG%2Fu5uGH4swzd561F%2BuhIT4%2BLnSuPsv9%2BJKIpjNr9dXYOyk7%2FBZrcjIT4eCnoKgedJP4BEqhG77E3NKP31FO7cfQA5K0dSYuLgz2TwCWJSOBzG6crzKK%2BohNfni%2Bx6OMUMMNe%2Fgf7ocbw0v0acKg6J8Ql0q%2BT%2FAXR5PNi5dz9c71upuQqCKFAD%2BYhrZLEAmpodaHO3Qy6TI3NhBpbrshGtOWKOSMYwYGQM8nJzoFJNxP2HjyIQho4PewK6hBktoDcUwtIln4PjOWzflQ%2Be5yl0yCCYgYikTclGlxadio%2BBQCSiW1UXoVGrKYwH4RgMrjU1HAB4vR6LzWYfFUCKxfS8Ftk5qxHoCUQAUkRJaSEokkV6Y%2F%2BJUOC4hn6A39NVXVBYeNP8piH6HeA4fPbpdBQV5KOx0QaL1YppX3Jgk0TwH2Vg6S3u%2BdB91%2B%2FpuNYPYFl5uP5V7ZqvsrX7jxqMXR6ff3gCQSTzFI0a1TX3wIs8ul%2Bq4HuWAAiM39vhOuR1O1fQ2gT%2F26Z8Z5vrl2OHi9OXZn995nLV9aFfS6UC9JeJPfuK0NBohWpCHMSAAsFe74WWP%2BvT25wtP9Bpob6uGqqyDnOtaeumjRu%2ByFu36VntK%2FPA5umTJeUtPWZSU9BCgud661odVp3DZtkc7AnYR33RRC708PrVi1larW7XwZIjLnd7R6SgSqWSNjU1B3F72pz5TZbXmX5vV81Yb7Lg7XT%2FUXriu8XLVqw6c6XqWnBKiiYU%2BMt3wWF7u7i91XlSEITwSAZ%2FCzAAHsJVbwXYFFEAAAAASUVORK5CYII%3D)](https://www.gnu.org/software/bash/)
[![Ubuntu 22.10](https://img.shields.io/badge/Ubuntu-22.10-brightgreen)](https://releases.ubuntu.com/kinetic/)
[![Become a sponsor to JV-conseil](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/JV-conseil "Become a sponsor to JV-conseil")
[![Follow JV conseil on StackOverflow](https://img.shields.io/stackexchange/stackoverflow/r/2477854)](https://stackoverflow.com/users/2477854/jv-conseil "Follow JV conseil on StackOverflow")
[![Follow JVconseil on Twitter](https://img.shields.io/twitter/follow/JVconseil.svg?style=social&logo=twitter)](https://twitter.com/JVconseil "Follow JVconseil on Twitter")
[![Follow JVconseil on Mastodon](https://img.shields.io/mastodon/follow/109896584320509054?domain=https%3A%2F%2Ffosstodon.org)](https://fosstodon.org/@JVconseil "Follow JVconseil@fosstodon.org on Mastodon")
[![Follow JV conseil on GitHub](https://img.shields.io/github/followers/JV-conseil?label=JV-conseil&style=social)](https://github.com/JV-conseil "Follow JV-conseil on GitHub")
<!--
[![License BSD 3-Clause](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](LICENSE)
[![Python 3.11](https://img.shields.io/badge/Python-3.11-green)](https://www.python.org/downloads/release/python-3112/)
[![PostgreSQL 14.6](https://img.shields.io/badge/PostgreSQL-14.6-green.svg)](https://www.postgresql.org/docs/14.6/)
<img alt="https://img.shields.io/badge/stack-overflow-orange.svg" src="https://img.shields.io/badge/stack-overflow-orange.svg">
-->

> _The only way to really learn scripting is to write scripts -- [Mendel Cooper](https://tldp.org/LDP/abs/html/index.html)_
>
> _Writing shell scripts leaves a lot of room to make mistakes, in ways that will cause your scripts to break on certain input, or (if some input is untrusted) open up security vulnerabilities... The simplest step is to avoid using shell at all -- [MIT Student Information Processing Board][MIT Student Information Processing Board]_

<!-- omit in toc -->
## Table of Content

- [Extract a substring from a string](#extract-a-substring-from-a-string)
- [Extract a value from a file](#extract-a-value-from-a-file)
- [Read a JSON stream](#read-a-json-stream)
- [Tools for Shell Script Development ⚙️](#tools-for-shell-script-development-️)
- [Features 🔎](#features-)
- [Coding Guidelines, Style, Linter ✍️](#coding-guidelines-style-linter-️)

## Extract a substring from a string

With `grep -Eo` and a [regex](https://regex101.com/library/wUcSv4) pattern

```bash
grep -Eo "http[^ ']+" <<EOF
curl 'https://cloud.sdu.dk/api/ingresses/browse?itemsPerPage=100&includeOthers=true&sortDirection=ascending'
-H 'Accept-Language: en-US,en;q=0.5'
-H 'Accept-Encoding: gzip, deflate, br'
-H 'Authorization: Bearer ****'
-H 'Content-Type: application/json; charset=utf-8'
-H 'Cookie: refreshToken=cf6220bd%2D650c%2D4a48%2D9836%2D58ea9ecb7567'
-H 'Sec-Fetch-Dest: empty'
-H 'Sec-Fetch-Mode: cors'
-H 'Sec-Fetch-Site: same-origin'
-H 'Pragma: no-cache'
-H 'Cache-Control: no-cache'
EOF
```

will output

```bash
https://cloud.sdu.dk/api/ingresses/browse?itemsPerPage=100&includeOthers=true&sortDirection=ascending
```

_src 👉 [stackoverflow.com](https://stackoverflow.com/a/13373256/2477854)_

## Extract a value from a file

Example of a pyproject.toml file

```toml
[tool.poetry]
name = "docs"
version = "0.1.0"
description = "Collection of Cheatsheets 🗒️ PostgreSQL 🐘, Git..."
repository = "https://github.com/JV-conseil/docs"
```

With `grep` and `sed`

```bash
grep -Eo "^repository.+$" pyproject.toml | sed -E 's/^repository = "(.+)"$/\1/'
```

will output

```bash
https://github.com/JV-conseil/docs
```

## Read a JSON stream

With `jq`

```bash
curl 'https://cloud.sdu.dk/api/ingresses/browse?itemsPerPage=100&includeOthers=true&sortDirection=ascending' \
-H 'Accept-Language: en-US,en;q=0.5' \
-H 'Accept-Encoding: gzip, deflate, br' -H 'Authorization: Bearer *****' \
-H 'Content-Type: application/json; charset=utf-8' \
--compressed | jq '.items[].specification.domain' >~/Downloads/example.json
```

will output

```bash
"app-9a7f8023b8b09392140f3ff9f12c91f2.cloud.sdu.dk"
"app-githubbing.cloud.sdu.dk"
"app-health-check.cloud.sdu.dk"
"app-health-status.cloud.sdu.dk"
"app-mission-ocean.cloud.sdu.dk"
"app-research-funding.cloud.sdu.dk"
"app-santa-maria-josefina-do-coracao-de-jesus-sancho-de-guerra.cloud.sdu.dk"
"app-thalassa.cloud.sdu.dk"
"app-yerun.cloud.sdu.dk"
```

_src 👉 [jq/manual](https://stedolan.github.io/jq/manual/)_

## Tools for Shell Script Development ⚙️

| <img src="https://timonwong.gallerycdn.vsassets.io/extensions/timonwong/shellcheck/0.29.4/1676233151659/Microsoft.VisualStudio.Services.Icons.Default" height="50" style="margin:.5rem">        | [ShellCheck](https://marketplace.visualstudio.com/items?itemName=timonwong.shellcheck)<br>Integrates [ShellCheck](https://github.com/koalaman/shellcheck) into VS Code, a linter for Shell scripts                                                                                  |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <img src="https://foxundermoon.gallerycdn.vsassets.io/extensions/foxundermoon/shell-format/7.2.5/1676969811685/Microsoft.VisualStudio.Services.Icons.Default" height="50" style="margin:.5rem"> | [**shell-format**](https://marketplace.visualstudio.com/items?itemName=foxundermoon.shell-format)<br>A formatter for shell scripts implementing [shfmt](https://github.com/mvdan/sh) parser, formatter, and interpreter<br>See [Google Shell Style Guide][Google Shell Style Guide] |

<!-- omit in toc -->
## General 📚

- [Bash Reference Manual](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html) - The definitive reference on shell behavior
- [Advanced Bash-Scripting Guide](https://tldp.org/LDP/abs/html/index.html) - An in-depth exploration of the art of shell scripting by Mendel Cooper
- [Awesome Bash](https://github.com/awesome-lists/awesome-bash) - A curated list of delightful Bash scripts and resources
- [Shell Scripting for Beginners](https://www.freecodecamp.org/news/shell-scripting-crash-course-how-to-write-bash-scripts-in-linux/) - How to Write Bash Scripts in Linux

## Features 🔎

- The Ultimate Guide to [Modularizing Bash Script Code](https://medium.com/mkdir-awesome/the-ultimate-guide-to-modularizing-bash-script-code-f4a4d53000c2) by Shinichi Okada
- How to use a [key-value dictionary](https://www.xmodulo.com/key-value-dictionary-bash.html) in Bash
- Bash [Parameter expansions](https://devhints.io/bash#parameter-expansions)

## Coding Guidelines, Style, Linter ✍️

- [Google Shell Style Guide][Google Shell Style Guide] revision 2.02
- The [Unofficial Bash Strict Mode](http://redsymbol.net/articles/unofficial-bash-strict-mode/) - _These lines deliberately cause your script to fail. Wait, what? Believe me, this is a good thing..._
- [Writing Safe Shell Scripts][MIT Student Information Processing Board] - MIT Student Information Processing Board

<!-- omit in toc -->
## Sponsorship

If this project helps you, you can offer me a cup of coffee ☕️ :-)

[![Become a sponsor to JV-conseil](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/JV-conseil)

<!-- links -->
[Google Shell Style Guide]: https://google.github.io/styleguide/shellguide.html
[MIT Student Information Processing Board]: https://sipb.mit.edu/doc/safe-shell/
