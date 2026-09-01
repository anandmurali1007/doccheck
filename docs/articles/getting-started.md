# Getting started with the sync test

This article is the baseline for the GitHub to Document360 sync test. It uses
only plain headings and paragraphs, so any rendering problem here points at the
sync pipeline rather than at a specific Markdown feature.

## What this article set covers

The `docs/articles` folder holds five short articles. Each one isolates a
different group of Markdown features so that a failure can be traced to a
single construct instead of a whole document.

## How the sync works

Document360 pulls content from the `main` branch of the connected repository.
The sync is one-way: GitHub is the source of truth, and the synced articles are
read-only inside Document360. Editing an article in the portal is not possible,
so every correction has to be committed back to this repository.

## What to verify after the first sync

Confirm that four articles appear under a category named after the `articles`
folder, and that the fifth one, which sits in `articles/advanced`, appears under
a nested sub-category of the same name rather than being flattened alongside the
others. Check that the article titles match the headings used in each file. Then
change a single paragraph, commit it, and check that the update reaches the
portal.

## Known limitations

Revision history and change tracking are not available for synced articles, and
only the `main` branch is picked up. Media files placed outside
`docs/.document360/assets` will not render.
