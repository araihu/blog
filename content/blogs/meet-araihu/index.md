+++
title = "Meet Arai Hû"
description = "Practical, open software in Go, and the decisions behind the tools we build."
language = "en"
authors = ["Arai Hû"]
tags = ["Open source"]
cover = "./assets/cover-v1.webp"
cover_alt = "A storm cloud sends a lime-green bolt into connected software modules with interface, monitoring and database symbols."
draft = false
publishedAt = "2026-10-31T23:48:31-03:00"
+++

Arai Hû brings together independent, open software projects built in Go. Our work covers server-rendered interfaces, API publishing and self-hosted monitoring. This blog is a place to explain that work beyond a release note or a README.

The name comes from Guarani. On our [organization website](https://araihu.com/en/), we describe *arai hû* as a black or dark cloud. The line that accompanies it is "Software for stormy weather." It is a useful image for the kind of work we care about: practical tools for problems that do not disappear when a demo ends.

## Useful on their own, better together

The projects share a simple direction. Each should solve a concrete problem on its own, while remaining useful alongside the others. Go is a common foundation, and server-rendered interfaces are a recurring choice.

[Goshtoso](https://github.com/araihu/goshtoso) provides UI components for Go applications built with templ. [Goshtoso App Shells](https://github.com/araihu/goshtoso-app-shells) adds reusable application layouts, and [Goshtoso Charts](https://github.com/araihu/goshtoso-charts) provides charts for Go and templ applications.

[Manja](https://github.com/araihu/manja) works with OpenAPI documentation and publishing. [Balemoh](https://github.com/araihu/balemoh) focuses on self-hosted monitoring. They address different jobs, with interfaces built on the same UI foundations.

Publishing is another part of that work. [Margo](https://github.com/araihu/margo) compiles Markdown into HTML, PDF and static slide decks. [Gazeta](https://github.com/araihu/gazeta) adds the editorial rules for a Git-managed blog. This blog is one consumer of those tools. Its articles and identity live in a separate repository, while the reusable publishing behavior stays upstream.

## What belongs here

We will use this space for project notes, explanations of design choices and accounts of experiments. A release announcement can say what changed. An article can explain which problem led to it, what we tried and where the result still has limits.

The code and project documentation remain the place to check current behavior. A post records a particular decision or stage of a project; it is not a substitute for the repository or a promise about future releases.

This introduction is available in English, Brazilian Portuguese and Spanish. Each version has its own address, and the language links lead to the corresponding article when a translation exists.

## Follow the work

Start with the [project overview](https://araihu.com/en/) or browse the [Arai Hû repositories](https://github.com/araihu). For a question, idea or bug report, open a discussion or issue in the relevant project when that channel is available. Keeping the conversation with the code makes it easier to follow what happens next.

Welcome to the blog.
