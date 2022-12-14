# Figurl interactive documents

## Overview

Figurl's interactive documents provide a new way of presenting scientific data, with text and interactive figures embedded together in one document. Authors can create and develop documents on their local machine, share them on GitHub, and archive them on Zenodo. Readers are able to explore and visualize the data in greater detail, while also gaining access to the scientific explanations that accompany them.

The interactive documents are simply markdown files with embedded figurl links that are rendered through figurl.org. Here is a [work-in-progress Figurl document](https://doc.figurl.org/gh/dcmnts/isosplit-paper/blob/main/isosplit.md) -- scroll down to the Results section to see the embedded figures.

There are three modes for working with these documents:

1. Develop locally

The author can develop the Figurl manuscript on their local machine with live refresh. Simply create a markdown document example.md and then run

```bash
figurl-to-html view-doc example.md
```

This starts a local web service and prints a localhost web address for viewing the document as it is developed.

2. Share

The author can share their Figurl manuscript by hosting it on github. To view the rendered manuscript, visit `https://doc.figurl.org/gh/owner/repo/blob/branch/example.md` filling in the path as appropriate.

3. Archive/Publish

Once the document is fully developed, the author can archive/publish their Figurl manuscript using figurl-to-html. This tool creates an output directory with all data and HTML needed to render the document, and does not depend on figurl.org nor doc.figurl.org. This output directory can then be stored on Zenodo and served with the help of a website called zenmirror.org. Simply run

```
figurl-to-html create-doc --input example.md --output example_folder
```

## Embedding Figurl figures in markdown

To include a Figurl figure inside markdown, simply paste in the URL as a separate paragraph. When rendered through doc.figurl.org, that paragraph will be replaced by the embedded figure. See [this example](https://github.com/dcmnts/isosplit-paper/blob/main/isosplit.md) -- scroll down to the Results section to see the embedded figures.

For example, if this file is being rendered through doc.figurl.org, then you will see the following as an embedded figure:

https://figurl.org/f?v=gs://figurl/bluster-views-1&d=sha1://ebcb6b4cda6f756f79dcc20c7c09f6d6b2ad0372&label=Bluster:%20Isosplit%20demo

## Figure captions

Figure captions are supported using the `<figure>` and `<figcaption>` html tags. See the above example.

## Citations

Citations are supported - see the above example. You can auto-generate the bibliography based on the inline citations and a .bib file using the `generate-doc-bibliography` command of `figurl-to-html`.

## LaTeX

Embedded LaTeX is supported using MathJax, just as it is [on GitHub](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions).

## Figure height

While the width is always set to 100%, the height of an embedded figure can be specified in the markdown file using yaml syntax within a comment directly below the figURL. See the above example to see how this is done.

## Upload to Zenodo

The figurl-to-html package provides a tool for uploading a standalone Figurl document to Zenodo. This document is then archived and can be viewed using zenmirror.org. More details will be provided in the future.
