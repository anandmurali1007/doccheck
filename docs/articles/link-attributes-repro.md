# Link attribute syntax repro

Repro for the reported issue where `target=_blank` is rendered as visible text
on articles synced from GitHub. Each case below is the same link with a
different attribute-quoting style. View this article on the Knowledge Base site
and record which cases render as a link and which leak literal text.

## Case 1 - backticks (the customer's syntax)

[Sysdig Secure](https://www.sysdig.com/products/platform){target=`_blank`}

Expected failure: the backticks are consumed as an inline code span before the
attribute block is parsed, so the braces leak as text.

## Case 2 - double quotes

[Sysdig Secure](https://www.sysdig.com/products/platform){target="_blank"}

Expected: renders as a link that opens in a new tab.

## Case 3 - unquoted value

[Sysdig Secure](https://www.sysdig.com/products/platform){target=_blank}

Expected: renders as a link that opens in a new tab.

## Case 4 - single quotes

[Sysdig Secure](https://www.sysdig.com/products/platform){target='_blank'}

Expected: renders as a link, but check the attribute value in devtools. The
quotes may be kept literally, giving `target="'_blank'"`, which is not a valid
target value even though nothing leaks into the visible text.

## Case 5 - raw HTML anchor

<a href="https://www.sysdig.com/products/platform" target="_blank">Sysdig Secure</a>

Expected: renders as a link if inline HTML is allowed on the sync path.

## Case 6 - attribute block plus a real code span

Text with `real code` and a link [Sysdig](https://www.sysdig.com){target="_blank"}.

Expected: the code span renders as code and the link still gets its attribute.
This separates "backticks are broken" from "code spans near attributes are
broken".

## Case 7 - Document360 callout, top level

:::(Warning) (Callout at top level)
This checks whether the callout extension runs on the GitHub sync path at all.
:::

## Case 8 - Document360 callout, indented inside a list

1. First step.
2. Second step.
    :::(Info) (Indented callout)
    The customer's article nests callouts inside numbered steps at this
    indentation. Check whether it renders as a callout or leaks as text.
    :::
3. Third step.
