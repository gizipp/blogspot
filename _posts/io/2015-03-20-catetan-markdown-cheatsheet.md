---
layout: post
title: "Catetan Markdown (Cheatsheet)"
shorttitle: "Catetan Markdown (Cheatsheet)"
description: "Catetan Markdown cheatsheet kalau-kalau lupa-lupa ingat."
category: io
tags: [markdown]
---

## Heading

    # H1
    ## H2
    ### H3
    #### H4
    ##### H5
    ###### H6

## Emphasis

    Emphasis, aka italics, with *asterisks* or _underscores_.
    Strong emphasis, aka bold, with **asterisks** or __underscores__.
    Combined emphasis with **asterisks and _underscores_**.
    Strikethrough uses two tildes. ~~Scratch this.~~

## Links

    [I'm an inline-style link](https://www.google.com)

    [I'm an inline-style link with title](https://www.google.com "Google's Homepage")

    [I'm a reference-style link][Arbitrary case-insensitive reference text]

    [I'm a relative reference to a repository file](../blob/master/LICENSE)

    [You can use numbers for reference-style link definitions][1]

    Or leave it empty and use the [link text itself]

    Some text to show that the reference links can follow later.

    [arbitrary case-insensitive reference text]: https://www.mozilla.org
    [1]: https://slashdot.org
    [link text itself]: https://www.reddit.com

## Images

    Here's our logo (hover to see the title text):

    Inline-style:
    ![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

    Reference-style:
    ![alt text][logo]

    [logo]: https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 2"


## Code and Syntax Highlighting

    ```javascript
    var s = "JavaScript syntax highlighting";
    alert(s);
    ```

    ```python
    s = "Python syntax highlighting"
    print s
    ```

    ```
    No language indicated, so no syntax highlighting.
    But let's throw in a <b>tag</b>.
    ```
