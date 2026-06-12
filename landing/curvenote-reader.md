---
title: Curvenote Reader
description: An openRxiv Labs experiment with Curvenote to layer interactive, web-native reading on top of the bioRxiv and medRxiv archives.
---

## Overview

openRxiv is experimenting with [Curvenote Reader](https://curvenote.com/products/reader), a product by [Curvenote](https://curvenote.com), to explore how preprints can become more useful at the point of reading. The experiment layers a web-native reader on top of existing bioRxiv and medRxiv content—without changing how authors submit or how the preprint archive is published.

Instead of downloading PDFs and hunting through references, readers can hover over citations, expand figures, and follow links to related work while staying in the flow of the article.

:::{important} Try Curvenote Reader in openRxiv Labs

You can try this experiment at:

https://reader.openrxivlabs.org

:::

## Hypothesis

Preprints are most valuable when readers can move easily from narrative to the evidence behind it—data, code, protocols, and cited work. We hypothesize that a connected reading experience, built on structured content already maintained by the archive, will help readers engage more deeply with preprints and discover related research without extra friction.

## How it works

Curvenote Reader transforms structured article metadata (for example, JATS XML) into an interactive reading layer on top of the existing preprint. Key capabilities include:

- **In-context citations** — see reference details and open-access links without leaving the article.
- **Expandable figures** — inspect figures and supporting material inline.
- **Web-native navigation** — read in the browser with a layout designed for screens, not print.

The experiment uses an automated handoff from existing archive formats, so it does not require authors or publishers to change submission workflows. Content is served on openRxiv-controlled infrastructure in line with [Labs operating principles](/index#operating-principles).

## Partner

This experiment is run in collaboration with **Curvenote**, whose mission is to improve how scientific content is authored, shared, and read on the web. Experiment materials and updates are maintained in the [curvenote-reader](https://github.com/openrxivlabs/curvenote-reader) repository on GitHub.

## Status and feedback

The experiment is active. If you try the reader or have feedback on the experience, reach out to [hello@openrxiv.org](mailto:hello@openrxiv.org) or open an issue in the [openRxiv Labs GitHub organization](https://github.com/openrxivlabs/curvenote-reader).

## Funding

This experiment is supported in part by a grant from [Alberta Innovates](https://albertainnovates.ca/) to [Curvenote](https://curvenote.com) for an international technology partnership with openRxiv. The partnership focuses on connected, web-native reading experiences for preprints.

## Project Updates

```{cn:articles}
:venue: labs
:collection: reader
:limit: 3
:show-thumbnails:
:show-date:
:show-authors:
```
