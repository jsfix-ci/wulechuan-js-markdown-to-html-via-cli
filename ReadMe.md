# Wulechuan's CLI Tool for Converting Markdown Files into HTML Files


## Multilingual Editions of this Article

- [简体中文版文档](./ReadMe.zh-hans-CN.md)




## NPM Page

<dl>
<dt>Package Name</dt>
<dd>

[@wulechuan/markdown-to-html-via-cli](https://www.npmjs.com/package/@wulechuan/markdown-to-html-via-cli)

</dd>
<dt>Author</dt>
<dd><p>wulechuan (南昌吴乐川)</p></dd>
</dl>




## Introduction

Yet another tool for converting MarkDown files into corresponding HTML files, but with gorgeous themes applied to the output HTML by default. The HTML includes both CSS rules and Javascript codes. **Thus, when deliver your article with the help of this tool, a single HTML file would be enough.**

> The Javascript codes are for the behviours of the table of contents(TOC) part.

> Note that although all CSS and Javascript contents are embeded, images are still external resources to the HTML.

This tool utilizes the ecosystem of the famous tool, "[markdownIt](https://www.npmjs.com/package/markdown-it)".

**You provide a set of markdown file paths, you get another set of HTML files.**

No need to provide literally anything, you get a full featured HTML. Including gorgeous themes, and responsive layout fitting all sizes of screens, and TOC with smart behaviours, and the pretty "back-to-top" button(an anchor in fact).


### Built-in Themes

The CSS file for the built-in theming is from another NPM package of mine, named "[@wulechuan/css-stylus-markdown-themes](https://www.npmjs.com/package/@wulechuan/css-stylus-markdown-themes)". See some pictures of an example article with the default theme applied [there](https://github.com/wulechuan/wulechuan-themes-for-htmls-via-markdowns/blob/master/docs/refs/en-US/application-examples.md).


## Installation

```bash
npm    i    -g    @wulechuan/markdown-to-html-via-cli
```


## Usage

### CLI Arguments

```bash
Usage: wlc-md-to-html [options]

Options:
  -v, --version
        Print the version of this program.

  -i, --from  [globs]
        Globs of any of:
          - one that matches `.md` files;
          - one that matches folders containing `.md` files;
          - a comma-separated values of above.
        Note that multiple presents of this argument is also allowed.
        (default: "./*.md")

  -o, --to  [path]
        Path of folder for output .html files. A single asterisk(*)
        is allowed at the beginning of the path, meaning the rest
        part of this path string will treat as a sub path to each
        and very source path. This is the ONLY special sign allowed
        in this path string. No question marks("?") are allowed.
        No asterisks are allowed in any other places of this string.
        (default: "./")

  -C, --config-json  [path]
        Specify a `.js` file to configure the conversions.
        (default: "./wlc-mk-to-html.config.js")

  -2, --concise-toc
        When presents, the max level of the TOC items in an HTML is
        limited to 2. This makes the TOC more concise and clean.
        Be aware that this way all deeper levels of TOC items are
        NEVER visible. They are hidden via CSS rules.

  -e, --expand-toc
        If the browser window is wide enough, expand the TOC panel when
        an HTML just loads. Note that either way, the TOC panel can
        ALWAYS toggle manually. Also Note that to expand the TOC panel
        is NOT the same thing as to expand an item of the TOC panel.

  -E, --toc-item-expanded-level  [level]
        If the browser window is wide enough, TOC items are collapsable
        and expandable, if it contains a nested TOC list. This option
        decides how many levels of TOC items are expanded by default.
        Note the all expandable items can ALWASY toggle manually.
        (default: "1")

  -l, --html-language  [language]
        Specified the value of the "lang" attribute of the <html>
        tag inside a generated HTML file.
        (default: "zh-hans-CN")

  -D, --debug
        To enable debugging mode.

  -h, --help                              output usage information

```


### Examples

-   To print some basic help info.

    ```bash
    wlc-md-to-html    --help
    ```

-   By default, this tool scans for all `.md` files under current folder, but **NOT** recursively searching sub-folders. And it outputs HTML files at the same folder.

    ```bash
    wlc-md-to-html
    ```

-   To build HTML files, each in the same sub-folder named "html" under the folder of its corresponding source markdown file. Notice the leading asterisk sign(`*`) in the output path.

    ```bash
    wlc-md-to-html    -i markdowns/*.md    -o "*/html/"
    ```

-   To build all HTML files into exactly the same output folder.

    ```bash
    wlc-md-to-html    -i ./**/*.md    -o ~/articles/html/
    ```

-   By default, this tool scans for all `.md` files under current folder, but **NOT** recursively searching sub-folders.

    ```bat
    wlc-md-to-html    -o C:\articles\
    ```


## TODOS

Nothing at present.



## License

WTFPL

> NOTE:
>
> I'm not an expert about license types. So I temporarily use WTFPL. But I guess this type of license might conflict with the ones used by those npm packages I'm utilizing.

