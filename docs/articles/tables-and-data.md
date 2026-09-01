# Tables and data

This article checks whether Markdown tables survive the sync, including
alignment and inline formatting inside cells.

## Simple table

| Setting | Value |
| --- | --- |
| Source | GitHub |
| Branch | main |
| Direction | One-way |
| Editable in portal | No |

## Table with alignment

| Field | Required | Notes |
| :--- | :---: | ---: |
| `docs` folder | Yes | Must sit at the repository root |
| `docs/.document360/assets` | Yes | Holds every media file |
| Article subfolder | Yes | Mirrored as a category |
| Config file | No | Not used by the integration |

## Table with formatting in cells

| Construct | Example | Expected result |
| --- | --- | --- |
| Bold | `**text**` | **text** |
| Italic | `*text*` | *text* |
| Inline code | `` `value` `` | `value` |
| Link | `[docs](https://docs.document360.com)` | [docs](https://docs.document360.com) |

## What to check

Column alignment, header separation, and cell-level formatting should all be
preserved. If a table collapses into a single paragraph, the sync is dropping
the pipe-table syntax.
