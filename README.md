# [MD]unmeris

###### A Translation Starter-Guide and Markdown Project for Morrowind

---

## View on [GitHub.io](https://mmillar-bolis.github.io/MDunmeris/)

Markdown is a plain-text language that makes writing formatted documents very easy. It's also possible to call custom fonts in Markdown using in-line HTML. By incorporating one of the available online dialects, it's very easy to quickly produce shareable documents in Dunmeris, the language of the people of Morrowind.

[Try the template!](https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0)

Note: *GitHub's ReadMe view will not load custom fonts. Please use* [github.io](https://mmillar-bolis.github.io/MDunmeris/) *for more about Dunmeris and the Daedric script.*

|![Trigon](assets/images/symbols/trigon_ghartok-256.png?raw=true "Trigon")|
|:-:|

##### Quick Info:
Want to skip the article and jump right in to creating and translating documents? Here's all you need:

- [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
- [Ayembedt font](https://github.com/georgd/OpenMW-Fonts)
- [Casual Dunmeris](https://casualscrolls.fandom.com/wiki/Dunmeri_language)
- [GitHub Template](https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0)

---

## Further Background

If you are unfamiliar with [John Gruber](https://daringfireball.net/projects/markdown/) and [Aaron Swartz](https://en.wikipedia.org/wiki/Aaron_Swartz)'s Markdown language, [have a look at it](https://www.markdownguide.org/getting-started/).

Markdown is a text formatting language that translates to strict HTML. The central focus and reason for the language is to store source text in the most human readable fashion possible but still be able to render it with formatted HTML.

Aside from the [Reference Specification](https://daringfireball.net/projects/markdown/), there are other slightly different dialects as well such as, [GitHub Flavored Markdown](https://github.github.com/gfm/) and [Pandoc Markdown](https://pandoc.org/MANUAL.html#pandocs-markdown).

However, all you really need to get started is something like [Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

*Could* one do all this with Word instead? Of course! However, one would need to have an office suite installed to their system. If that setup fit's your workflow, more power to you. This project is mostly focused on using plaintext editors instead of rich office ones.

---

## ToolKit

Markdown files are plain-text files with the extension, `.md`. As with HTML, any text editor, such as Notepad and TextEdit, can be used to create and edit markdown files. However, choosing a text editor that supports [syntax highlighting](https://en.wikipedia.org/wiki/Syntax_highlighting) will make things significantly easier to read.

In addition to a text editor, one will also need a way to view rendered markdown. A few viewer applications exist as well as some browser plugins. However, many major code editors also incorporate some form of markdown viewer these days as well.

- A Text Editor:
  - __Any plain-text editor, really!__
  - [Notepad2-mod](https://xhmikosr.github.io/notepad2-mod/)
  - [Micro](https://micro-editor.github.io/)
  - [GVim](https://www.vim.org/download.php#pc)

- A Markdown Viewer:
  - [MdView](https://github.com/c3er/mdview)
  - [Markdown Viewer](https://github.com/simov/markdown-viewer) browser extension
  - [mdless](https://brettterpstra.com/projects/mdless/) command-line tool
  - [glow](https://github.com/charmbracelet/glow) command-line tool

- Viewer/Editor:
  - [Visual Studio Code](https://code.visualstudio.com/Download)
  - [Notepad++](https://notepad-plus-plus.org/) with [MarkdownViewer++](https://github.com/nea/MarkdownViewerPlusPlus/releases)
  - [Atom](https://atom.io/) with [Markdown Preview](https://github.com/atom/markdown-preview)
  - [Typora](https://typora.io/)

---

## Fonts in Markdown

Knowing that Markdown files are translated into HTML, one can actually embed HTML directly into a document for edge-case needs. To do so goes a bit against the ethos behind the language, but it does reasonably introduces a way to rapid prototype tricky designs when pandoc is not available or you don't have template files to surround your markdown yet.

Adding a style tag to the beginning of your document will allow for adding some CSS to import a font. Below is an example of an HTML style tag with embedded CSS that declares a font:

```html
<style>
@font-face {
    font-family: Daedric;
    src: url("/path/to/Daedric.ttf") format('truetype');
    font-weight: medium;
    font-style: normal;
}
</style>
```

Optionally, if your markdown viewer does not allow for loading external fonts, you can convert the font to embeddable text using [Base64](https://en.wikipedia.org/wiki/Base64) and then insert that into your tag. Below I have changed the source to load text data from the URL path where *<BASE64_TEXT_CONTENTS>* is the ASCII conversion of a TrueType font:

```html
<style>
@font-face {
    font-family: Daedric;
    src: url(data:font/truetype;charset=utf-8;base64,<BASE64_TEXT_CONTENTS>) format('truetype');
    font-weight: medium;
    font-style: normal;
}
</style>
```

This will allow you to distribute a single, flat markdown file with fonts, similar to a `.pdf`. However, it is important to know that embedding fonts produces large text files, and these can be difficult to work with if not maintained. (For this project, I am only importing *loose* fonts.) In some rare cases, antiviral programs might regard embedded Base64 as suspicious.

Finally, you can render text in your Markdown body by wrapping it with a span tag that specifies the font by it's internal name (not filename):

```html
<span style="font-family:Daedric">makhel fahraj</span>
```

All one really needs to get started is this handy [GitHub template](https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0)! The documents within already contain this style element, one with the font embedded and the other with a reference to the loose `.ttf` font. They are ready for editing or viewing from a local markdown renderer, provided the font folder is kept with loose one.

---

## About This Font

I have borrowed the [Ayembedt font](https://github.com/georgd/OpenMW-Fonts) created by Georg Duffner for [OpenMW](https://openmw.org). I have modified, and recompiled it into a smaller TrueType font using [FontForge](https://fontforge.org/en-US/downloads/).

Both the compiled `.ttf` and the Base64 rendering, as well as it's source code with the modifications I have made are available in the assets directory of the GitHub repo.

## More Information

Head to [MDunmeris github.io](https://mmillar-bolis.github.io/MDunmeris/) page to see the html font rendering and translation starter-guide.

---

