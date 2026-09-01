# Code samples

This article checks fenced code blocks, language hints, and indentation.

## Shell

```bash
git add docs/
git commit -m "Add sync test articles"
git push origin main
```

## JSON

```json
{
  "source": "github",
  "branch": "main",
  "articlePath": "docs/articles",
  "assetPath": "docs/.document360/assets",
  "readOnly": true
}
```

## YAML

```yaml
sync:
  provider: github
  branch: main
  paths:
    articles: docs/articles
    assets: docs/.document360/assets
```

## C#

```csharp
public sealed class SyncResult
{
    public string Branch { get; init; } = "main";
    public int ArticlesSynced { get; init; }
    public bool IsReadOnly => true;
}
```

## Block without a language hint

```
docs/
  .document360/
    assets/
  articles/
    getting-started.md
```

## Indentation check

Leading spaces inside a fence must be kept exactly as written:

```text
level-1
    level-2
        level-3
```

## What to check

Language labels, syntax highlighting, and whitespace should all carry over. A
fence rendered as plain paragraph text means the code block was not recognised.
