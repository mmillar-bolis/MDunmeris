# [MD]unmeris

#### A Git Markdown Repository for Morrowind Related Documents

---

## View on [GitHub.io](https://mmillar-bolis.github.io/MDunmeris/)

Markdown is a plain-text language that makes writing formatted documents very easy. It's also possible to call custom fonts in Markdown using in-line HTML. By incorporating one of the available online dialects, it's very easy to quickly produce shareable documents in Dunmeris, the language of the people of Morrowind.

Note: *GitHub's ReadMe view will not load custom fonts. Please use* [github.io][1] *for more about Dunmeris and the Daedric script.*

|   Ghartok Trigon   |
|:------------------:|
|![Ghartok Trigon][2]|

[1]: https://mmillar-bolis.github.io/MDunmeris/
[2]: assets/images/symbols/trigon_ghartok-256.png

## Quick Info:

Want to skip the article and jump right in to creating and translating documents? Here's all you need:

- [Markdown][3]
- [Ayembedt font][4]
- [Casual Dunmeris][5]
- [GitHub Template][6]

[3]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
[4]: https://github.com/georgd/OpenMW-Fonts
[5]: https://casualscrolls.fandom.com/wiki/Dunmeri_language
[6]: https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0

---

## Further Background

If you are unfamiliar with [John Gruber][7] and [Aaron Swartz][8]'s Markdown language, [have a look at it][9].

Markdown is a text formatting language that translates to strict HTML. The central focus and reason for the language is to store source text in the most human readable fashion possible but still be able to render it with formatted HTML.

Aside from the [Reference Specification][10], there are other slightly different dialects as well such as, [GitHub Flavored Markdown][11] and [Pandoc Markdown][12].

However, all you really need to get started is something like [Adam Pritchard's Markdown Cheatsheet][13].

*Could* one do all this with Word instead? Of course! However, one would need to have an office suite installed to their system. If that setup fit's your workflow, more power to you. This project is mostly focused on using plaintext editors instead of rich office ones.

[7]: https://daringfireball.net/projects/markdown/
[8]: https://en.wikipedia.org/wiki/Aaron_Swartz
[9]: https://www.markdownguide.org/getting-started/
[10]: https://daringfireball.net/projects/markdown/
[11]: https://github.github.com/gfm/
[12]: https://pandoc.org/MANUAL.html#pandocs-markdown
[13]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

---

## Fonts in Markdown

Knowing that Markdown files are translated into HTML, one can actually embed HTML directly into a document for edge-case needs. To do so goes a bit against the ethos behind the language, but it does reasonably introduces a way to rapid prototype tricky designs when Pandoc is not available or you don't have template files to surround your markdown yet.

Adding a style tag to the beginning of your document will allow for adding some CSS to import a font. Below is an example of an HTML style tag with embedded CSS that declares a font:

```html
<style>
@font-face {
    font-family: HayghinDaedric;
    src: url("/path/to/HayghinDaedric.ttf") format('truetype');
    font-weight: medium;
    font-style: normal;
}
</style>
```

Optionally, if your markdown viewer does not allow for loading external fonts, you can convert the font to embeddable text using [Base64][14] and then insert that into your tag. Below I have changed the source to load text data from the URL path where *<BASE64_TEXT_CONTENTS>* is the ASCII conversion of a TrueType font:

```html
<style>
@font-face {
    font-family: HayghinDaedric;
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

All one really needs to get started is this handy [GitHub template][15]! The documents within already contain this style element, one with the font embedded and the other with a reference to the loose `.ttf` font. They are ready for editing or viewing from a local markdown renderer, provided the font folder is kept with loose one.

[14]: https://en.wikipedia.org/wiki/Base64
[15]: https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0

---

