---
sort: 5
title: Markdown
---

<!-- markdownlint-disable MD025 MD026 MD033 MD041 -->

<a href="https://daringfireball.net/projects/markdown/" target="_blank" title="Markdown By John Gruber"><img src="https://raw.githubusercontent.com/dcurtis/markdown-mark/master/svg/markdown-mark.svg" align="right" alt="Markdown By John Gruber" height="80" style="margin:1.5em 0 0 .5em"></a>

<!-- omit in toc -->
# Markdown

[![Become a sponsor to JV-conseil](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/JV-conseil "Become a sponsor to JV-conseil")
[![Follow JV conseil on StackOverflow](https://img.shields.io/stackexchange/stackoverflow/r/2477854)](https://stackoverflow.com/users/2477854/jv-conseil "Follow JV conseil on StackOverflow")
[![Follow JVconseil on Twitter](https://img.shields.io/twitter/follow/JVconseil.svg?style=social&logo=twitter)](https://twitter.com/JVconseil "Follow JVconseil on Twitter")
[![Follow JVconseil on Mastodon](https://img.shields.io/mastodon/follow/110950122046692405)](https://mastodon.social/@JVconseil "Follow JVconseil@mastodon.social on Mastodon")
[![Follow JV conseil on GitHub](https://img.shields.io/github/followers/JV-conseil?label=JV-conseil&style=social)](https://github.com/JV-conseil "Follow JV-conseil on GitHub")
<!--
[![License BSD 3-Clause](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](LICENSE)
[![Python 3.11](https://img.shields.io/badge/Python-3.11-green)](https://www.python.org/downloads/release/python-3112/)
[![PostgreSQL 14.6](https://img.shields.io/badge/PostgreSQL-14.6-green.svg)](https://www.postgresql.org/docs/14.6/)
<img alt="https://img.shields.io/badge/stack-overflow-orange.svg" src="https://img.shields.io/badge/stack-overflow-orange.svg">
-->

Interesting and advanced features of Markdown 👇

1. Table of Content generation w/ `<!-- omit in toc -->` to ignore first-level heading.
2. Image [positioning](https://github.com/DavidWells/advanced-markdown "Learn about advanced markdown techniques"): side-by-side, text-wrap, full-width.
3. Markdown Lint rules enforcing.
4. Footnotes `[^1]`
5. [Frontmatter](https://mystmd.org/guide/frontmatter#) allows you to specify metadata and options about how your project should behave or render.
6. Code Block language convention starting with `bash` or `py` or `js`
7. Table [formatting](https://github.com/yzhang-gh/vscode-markdown?tab=readme-ov-file#github-flavored-markdown "Table formatter") w/ [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) VS Code extension.
8. File Naming Convention... for convenient date sorting 👉 [How do you control the order in which files appear in a GitHub gist](https://stackoverflow.com/a/17668995/2477854 "How do you control the order in which files appear in a GitHub gist") 👀

## Recommended VS Code extensions ⚙️

|     <img src="https://davidanson.gallerycdn.vsassets.io/extensions/davidanson/vscode-markdownlint/0.55.0/1713329425871/Microsoft.VisualStudio.Services.Icons.Default" alt="markdownlint by David Anson" width="100">      | [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)<br>Markdown linting and style checking for Visual Studio Code scripts.                                                                                          |
| :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|        <img src="https://yzhang.gallerycdn.vsassets.io/extensions/yzhang/markdown-all-in-one/3.6.2/1705324444519/Microsoft.VisualStudio.Services.Icons.Default" alt="Markdown All in One by Yu Zhang" width="100">        | **[Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)**<br>All you need to write Markdown (keyboard shortcuts, table of contents, auto preview and more.                                                         |
| <img src="https://bierner.gallerycdn.vsassets.io/extensions/bierner/github-markdown-preview/0.3.0/1651533762167/Microsoft.VisualStudio.Services.Icons.Default" alt="GitHub Markdown Preview by Matt Bierner" width="100"> | **[GitHub Markdown Preview](https://marketplace.visualstudio.com/items?itemName=bierner.github-markdown-preview)**<br>Changes VS Code's built-in markdown preview to match GitHub. This is an extension pack of the following VS Code markdown preview extensions. |
|            <img src="https://bierner.gallerycdn.vsassets.io/extensions/bierner/emojisense/0.10.0/1686035362121/Microsoft.VisualStudio.Services.Icons.Default" alt=":emojisense: by Matt Bierner" width="100">             | **[:emojisense:](https://marketplace.visualstudio.com/items?itemName=bierner.emojisense)**<br>Adds suggestions and autocomplete for emoji.                                                                                                                         |

Recommended VS Code extensions in `~/GitHub/<owner>/<repo>/.vscode/extensions.json` 👇

```json
{
  "recommendations": [
    "bierner.emojisense",
    "davidanson.vscode-markdownlint",
    "yzhang.markdown-all-in-one",
    "bierner.github-markdown-preview",
  ]
}
```

Review your VS Code settings in 👇

1. `~/GitHub/<owner>/<repo>/.vscode/settings.json`
2. `~/Library/Application Support/Code/User/settings.json`

## Note, Tip, Warning

> [!NOTE]
> Please note that...

```txt
> [!NOTE]
> Please note that...
```

> [!TIP]
> If you wish to...

```tip
> [!TIP]
> If you wish to...
```

```txt
> [!TIP]
> If you wish to...
```

> [!WARNING]
>
> 1. When using...
> 2. This step is crucial as it ensures your database is properly mounted and prevents any loss of data.

```txt
> [!WARNING]
>
> 1. When using...
> 2. This step is crucial as it ensures your database is properly mounted and prevents any loss of data.
```

## References 📚

1. [Markdown and Visual Studio Code](https://code.visualstudio.com/docs/languages/markdown "Markdown and Visual Studio Code") several Markdown-specific features that help you be more productive.
2. [GitHub Flavored Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax "Create sophisticated formatting for your prose and code on GitHub with simple syntax") Style Guide to create sophisticated formatting for your prose and code on GitHub with simple syntax ✍️
3. [Markdown Syntax](https://daringfireball.net/projects/markdown/syntax "Markdown Syntax Documentation") by John Gruber co-creator of the Markdown markup language 🖋️
4. [Markdown Tutorial](https://github.com/luong-komorebi/Markdown-Tutorial/blob/master/README_fr.md) - En Français 🇫🇷

## Sponsorship

If this project helps you, you can offer me a cup of coffee ☕️ :-)

[![Become a sponsor to JV-conseil](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/JV-conseil)
