
---

|"ALMSIVI", fresco by [Tyddyner](https://tyddyner.tumblr.com/) \[[1](https://tyddyner.tumblr.com/post/127475780830/almalexia-godess-queen-of-morrowind-warden-lover), [2](https://tyddyner.tumblr.com/post/127579542465/sotha-sil-mystery-god-of-morrowind-the-last-one), [3](https://tyddyner.tumblr.com/post/127640108900/vivec-vehk-and-vehk-god-thief-and-god-poet)\]|
|---|
|![Tribunal](assets/images/fresco-256.png?raw=true "Tribunal")|

Markdown is a very easy language to write documents in. It's also possible to call custom fonts in Markdown using in-line HTML. By incorporating one of the available spoken dialects, it is very easy to quickly produce documents in Dunmeris (<span style="font-family:Daedric">dunmeris</span>), the language of the people of Morrowind. 

|Three blessings, sera|Walk with virtue|Why walk when you can ride?|
|---|---|---|
|Cahn'shoksunaa sera|Kosi enhi julopum|Ju'it khosi ku'elm ohn duhnanich?
|<span style="font-family:Daedric">cahn’shoksunaa sera</span>|<span style="font-family:Daedric">kosi enhi julopum</span>|<span style="font-family:Daedric">ju'it khosi ku'elm ohn duhnanich</span>

- [Example 2](Novena_for_the_Hortator.md)
- [Example 3](Old_Pilgrims_Oath.md)

## The Gist of It:
- Markdown
- [Ayembedt font](https://github.com/georgd/OpenMW-Fonts)
- [Casual Dunmeris](https://casualscrolls.fandom.com/wiki/Dunmeri_language)

## Background

If you are unfamiliar with [John Gruber](https://daringfireball.net/projects/markdown/) and [Aaron Swartz](https://en.wikipedia.org/wiki/Aaron_Swartz)'s Markdown language, [have a look at it](https://www.markdownguide.org/getting-started/).

Markdown is a text formatting language that translates to strict HTML. The central focus and reason for the language is to store source text in the most human readable fashion possible but still be able to render it with more ritch HTML.

Aside from the [Reference Specification](https://daringfireball.net/projects/markdown/), there are other slightly different dialects as well such as, [GitHub Flavored Markdown](https://github.github.com/gfm/) and [Pandoc Markdown](https://pandoc.org/MANUAL.html#pandocs-markdown).

However, all you really need to get started is something like [Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

## ToolKit

Markdown files are plaintext files with the extension, `.md`. As with HTML, any text editor, such as Notepad and TextEdit, can be used to create and edit markdown files. However, choosing a text editor that supports [syntax highlighting](https://en.wikipedia.org/wiki/Syntax_highlighting) will make things significantly easier to read.

In addition to a text editor, one will also need a way to view rendered markdown. A few viewer applications exist as well as some browser plugins. However, many major code editors also incorporate some form of markdown viewer these days as well.

A Text Editor:
- Any plain-text editor, really!
- [Notepad2-mod](https://xhmikosr.github.io/notepad2-mod/)
- [Micro](https://micro-editor.github.io/)
- [GVim](https://www.vim.org/download.php#pc)

A Markdown Viewer:
- [MdView](https://github.com/c3er/mdview)
- [Markdown Viewer](https://github.com/simov/markdown-viewer) browser extension
- [mdless](https://brettterpstra.com/projects/mdless/) command-line tool
- [glow](https://github.com/charmbracelet/glow) command-line tool

Viewer/Editor:
- [Visual Studio Code](https://code.visualstudio.com/Download)
- [Notepad++](https://notepad-plus-plus.org/) with [MarkdownViewer++](https://github.com/nea/MarkdownViewerPlusPlus/releases)
- [BBEdit](http://www.barebones.com/products/bbedit/)
- [Atom](https://atom.io/) with [Markdown Preview](https://github.com/atom/markdown-preview)
- [Typora](https://typora.io/)
- [Texts](http://www.texts.io/)
- [Abricotine](https://github.com/brrd/Abricotine)

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

 Furthermore, if your markdown viewer does not allow for loading external fonts, you can convert the font to embeddable text using [base64](https://en.wikipedia.org/wiki/Base64) and then insert that into your tag. Below I have changed the source to load text data from the url path:

```html
    src: url(data:font/truetype;charset=utf-8;base64,<BASE64_CONTENTS>) format('truetype');
```

Finally, you can render text in your Markdown body by wrapping it with a span tag that specifies the font by it's internal name (not filename):

```html
<span style="font-family:Daedric">makhel fahraj</span>
```

Nomally, I would not advocate for embedding binary files into your documents as, aside from potential security concerns, it produces rather large text files.

However, imagine you are a novice programmer in a scenario where you are still figuring out the whole pandoc thing and you just want to casually mess with a cool font here or there as you create shareable lore for others based on some old RPG. Daedric has no unicode script, registered or non. It currently only exists as a font replacement to US/English and thus is a bit tricky to portably incorporate into something like Markdown. I'm hoping this is a compromise to attract interest in both using Markdown and writing in Daedric.

Unfortunately, there is no way to manually change the size of text in any implementation of markdown. For that, you will need to turn to a more explicit typsetting language or just regular HTML and CSS.

In addition to this readme, I have included other `.md` files that contain the ebmedded Daedric font. I hope to make it as easy as possible for interested editors to start writing and sharing.

## About This Font

I have borrowed the [Ayembedt font](https://github.com/georgd/OpenMW-Fonts) created by Georg Duffner for [OpenMW](https://openmw.org), modified, and recompiled it into a smaller TrueType font using [FontForge](https://fontforge.org/en-US/downloads/).

Both the compiled `.ttf` and the base64 rendering, as well as it's source code are available in the included assets directory. In addition, I have included loose css files: one containing the base64 version of the font and the other pointing to the loose file.

## Language Guidelines Used

The language dialect I have chosen for most of my translations is the continually expanding [Casual Dunmeris](https://casualscrolls.fandom.com/wiki/Dunmeri_language), so named because of the wiki it comes from: [Casual Scrolls](https://casualscrolls.fandom.com/).

There is a lot of activity surrounding this dialect and it seems very well developed. When translating cultural adages of Morrowind, Casual Dunmeris rolls with off the tongue rather well.

|Learn by serving|
|---|
|Viya ru yilakam|
|<span style="font-family:Daedric">viya ru yilakam</span>|

I tend to refer to it as *Tretke* dialect (Slovak for "trinket") to pay tribute to the username of the forum's founder and original publisher of the language, [Matthew Knight](https://casualscrolls.fandom.com/wiki/User:Mknightretke).

It is unclear (to me at least) who specifically originally collaborated on the language, but it appears that around 2011, a framework was designed for the members of the [original party](https://casualscrolls.fandom.com/wiki/Casual_Elder_Scrolls_Wiki#Characters) of a [PbP](https://en.wikipedia.org/wiki/Play-by-post_role-playing_game) Elder Scrolls campaign that was being recorded on the Casual Scrolls wiki.

The wiki itself is still being updated, revised, and expanded to suit the continuing needs of Dunmeris writers and speakers.

As the wiki has recommended, I have taken some liberties here and there to deliberately construct a simpler sentences in Dunmeris. As the culture is *very* high-context, it seems proper that much of the language information is implicit.

Since Tretke is still new and developing, I have taken to inventing words as the need arises, based on already available nouns and verbs.

I am *not* a language expert and am very much learning as I go, so feel free to let me know where sentences or phrases could stand to be modified.

In addition, it helps to more clearly distinguish this form of Dunmeris from Hrafnir's [Ald Redoranis](https://www.imperial-library.info/content/hrafnirs-languages-nordic#Dunmeris), which is another notable dialect from the fourth era.

---

## About the Trigrammaton

The central religious symbol of the Tribunal Faith is the Ghartok Triolith, represented as an inverse triangle with Daedric glyphs in each corner, spelling *ASV*. However, it can also be common to see the [Imperial Triolith](https://en.uesp.net/wiki/File:MW-cover-Morrowind_Box_Art.jpg) which features the Seal of Akatosh instead of the Hand of Mephala at it's center.

|Ghartok Triolith (Clearly, I am no graphic designer.)|
|---|
|![Triolith](assets/images/triolith-256.png?raw=true "Triolith")|

The word "ALMSIVI" is a *portmanteau* of the three individual names of the Godhead. However, the letters themselves are merely a roman rendering of the phonetic pronounciation of the daedric glyphs, <span style="font-family:Daedric; color:red">ASV</Span>.

The word itself, literally unprnouncable by Dunmer, comes from [Ehlnofex](https://en.uesp.net/wiki/Lore:Ehlnofex_Languages). The *portmanteau* form is simply the closest one can come to pronouncing a word in a divine language.

|ALMSIVI in every hour|
|---|
|ASV gher alni telsan|
|<span style="font-family:Daedric; color:red">ASV</Span><span style="font-family:Daedric"> gher alni telsan</span>|

The fact that words in Ehlnofex are fluid would support the custom that surrounds the Trigrammaton, concerning the centering of the Daedric character for the respective deity in their regions of worship.

For example, in the Holy City of Vivec, ALMSIVI is rendered, \"<span style="font-family:Daedric; color:red">AVS</Span>\" while in the Holy Capitol of Mournhold, it is rendered \"<span style="font-family:Daedric; color:red">SAV</Span>.\" In all places, it is still pronounced the same.

To render text in red, specify the color in the span tag like so:

```html
<span style="font-family:Daedric; color:red">ASV</Span>
```

Based on the textual examples that I have seen, it would appear that red is the honorific color to represent holy words or even words of *grave* importance. As a matter of propriety, I try to only highlight the names of the holiest figures and only where it seems culturally appropriate. Your interpretation may vary.

For a better understanding of the symbolic thought influencing this mysterious three letter word, see the [Tetragrammaton](https://en.wikipedia.org/wiki/Tetragrammaton) as well as the article on Ehlnofex. Also have a look at [Earthsea](https://en.wikipedia.org/wiki/A_Wizard_of_Earthsea) and it's use of *Rumpelstiltskin theory* or the idea that true words may have power. There seems to be  similar theme in many Tamrielic religions.

The Tribunal Faith and it's influence on Dunmer culture cannot be understated. To learn more about it, have a look at [The New Whirling School](https://www.newwhirlingschool.com/intro.php) which features a great introduction, [exploratory essays](https://www.newwhirlingschool.com/intro.php#essays), and the first commentary on a central scripture, [*The Lessons*](https://en.uesp.net/wiki/Morrowind:The_36_Lessons_of_Vivec) (<span style="font-family:Daedric">as shoreshiik</span>, *As Shoreshiik*, more commonly known to as *The 36 Lessons of Vivec*).

## Publishing Your Work

TODO: Demonstrate

- export to pdf
- pandoc
- github

---

|The ending of the words is ALMSIVI|
|---|
|As dimihn am as edur ASV|
|<span style="font-family:Daedric">as dimihn am as edur </span><span style="font-family:Daedric; color:red">ASV</Span>|

---

