
---

<center>
<a href="index.html">Home</a>&nbsp;&nbsp;&nbsp;&nabla;&nbsp;&nbsp;&nbsp;<a href="archive.html">Archive</a>&nbsp;&nbsp;&nbsp;&nabla;&nbsp;&nbsp;&nbsp;<a href="https://github.com/mmillar-bolis/MDunmeris">GitHub</a>
</center>

---

Markdown is a plain-text language that makes writing formatted documents very easy. It's also possible to call custom fonts in Markdown using in-line HTML. By incorporating one of the available online dialects, it's very easy to quickly produce shareable documents in Dunmeris (<span style="font-family:Daedric">dunmeris</span>), the language of the people of Morrowind.

[Try the template!](https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0) Some translation examples:

|Three blessings, sera|Walk with virtue|Why walk when you can ride?|
|:-:|:-:|:-:|
|Cahn'shoksunaa sera|Kosi enhi julopum|Ju'it khosi ku'elm ohn duhnanich?
|<span style="font-family:Daedric">cahn’shoksunaa sera</span>|<span style="font-family:Daedric">kosi enhi julopum</span>|<span style="font-family:Daedric">ju'it khosi ku'elm ohn duhnanich</span>


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

Markdown files are plaintext files with the extension, `.md`. As with HTML, any text editor, such as Notepad and TextEdit, can be used to create and edit markdown files. However, choosing a text editor that supports [syntax highlighting](https://en.wikipedia.org/wiki/Syntax_highlighting) will make things significantly easier to read.

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

Optionally, if your markdown viewer does not allow for loading external fonts, you can convert the font to embeddable text using [base64](https://en.wikipedia.org/wiki/Base64) and then insert that into your tag. Below I have changed the source to load text data from the url path where *<BASE64_TEXT_CONTENTS>* is the ASCII conversion of a TrueType font:

```html
    src: url(data:font/truetype;charset=utf-8;base64,<BASE64_TEXT_CONTENTS>) format('truetype');
```

This will allow you to distribute a single, flat markdown file with fonts, similar to a `.pdf`. However, it is important to know that embedding fonts produces large text files, and these can be difficult to work with if not maintained. (For this project, I am only importing *loose* fonts.) In some rare cases, antiviral programs might regard embedded base64 as suspicious.

Finally, you can render text in your Markdown body by wrapping it with a span tag that specifies the font by it's internal name (not filename):

```html
<span style="font-family:Daedric">makhel fahraj</span>
```

All one really needs to get started is this handy [GitHub template](https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0)! The documents within already contain this style element, one with the font embedded and the other with a reference to the loose `.ttf` font. They are ready for editing or viewing from a local markdown renderer, provided the font folder is kept with loose one.

---

## About This Font

I have borrowed the [Ayembedt font](https://github.com/georgd/OpenMW-Fonts) created by Georg Duffner for [OpenMW](https://openmw.org). I have modified, and recompiled it into a smaller TrueType font using [FontForge](https://fontforge.org/en-US/downloads/).

Both the compiled `.ttf` and the base64 rendering, as well as it's source code with the modifications I have made are available in the assets directory of the GitHub repo.

---

## Language Guidelines Used

The language dialect I have chosen for most of my translations is the continually expanding [Casual Dunmeris](https://casualscrolls.fandom.com/wiki/Dunmeri_language), so named because of the wiki it comes from: [Casual Scrolls](https://casualscrolls.fandom.com/).

There is a lot of activity surrounding this dialect and it seems very well developed. When translating cultural adages of Morrowind, Casual Dunmeris rolls with off the tongue rather well.

I like to refer to it as *Tretke* dialect (Slovak for "trinket") to pay tribute to the username of the forum's founder and original publisher of the language, [Matthew Knight](https://casualscrolls.fandom.com/wiki/User:Mknightretke).

It is unclear (to me at least) who specifically originally collaborated on the language, but it appears that around 2011, a framework was designed for the members of the [original party](https://casualscrolls.fandom.com/wiki/Casual_Elder_Scrolls_Wiki#Characters) of a [PbP](https://en.wikipedia.org/wiki/Play-by-post_role-playing_game) Elder Scrolls campaign that was being recorded on the Casual Scrolls wiki.

The wiki itself is still being updated, revised, and expanded to suit the continuing needs of Dunmeris writers and speakers.

As the wiki has recommended, I have taken some liberties here and there to deliberately construct simpler sentences in Dunmeris. As the culture is *very* high-context, it seems proper that much of the language information appear implicit. Looking at examples such as the [Words of the Wind](https://en.uesp.net/wiki/Lore:Words_of_the_Wind) and [The Book of Dawn and Dusk](https://en.uesp.net/wiki/Lore:The_Book_of_Dawn_and_Dusk), I have also structured some phrases like prayers or poetry. Anything that seems common should just roll off the tongue, in my opinion.

|Learn by serving|
|:-:|
|Viya ru yilakam|
|<span style="font-family:Daedric">viya ru yilakam</span>|


Following the [lineage of Ehlnofex languages](https://en.uesp.net/wiki/Lore:Ehlnofex_Languages), one can see that Dunmeris is derived from Aldmeris. If anyone has further interest, for an additional translation guide, resource, and inspiration, there is a fascinating project to [document Aldmeris](https://tes-sandbox.fandom.com/wiki/Aldmeris_(Language)).

In addition, there is also another dialect of Dunmeris, as documented by [HrafnirII](https://www.imperial-library.info/users/hrafnir-ii), called [Ald Redoranis](https://www.imperial-library.info/content/hrafnirs-languages-nordic#Dunmeris), which is notable for being from the fourth era.

Since Casual Dunmeris is still new and developing, I have also taken to inventing words as the need arises, based on already available nouns and verbs that I smash together.

---

## Religion and Morrowind

|[Ghartok](https://www.imperial-library.info/content/forum-archives-michael-kirkbride#node-2865:~:text=What%20does%20%22GHARTOK%22%20mean%3F) Triolith|
|:-:|
|![Triolith](assets/images/triolith-256.png?raw=true "Triolith")|


## About the Triolith Symbol

The central religious symbol of the Tribunal Faith is the depiction of the [Triolith](https://d2skuhm0vrry40.cloudfront.net/2019/articles/2019-05-22-11-21/Lessons4.jpg/EG11/resize/690x-1/quality/75/format/jpg), represented as an inverse triangle with Daedric glyphs in each corner, spelling *ASV*. However, it can also be common to see many variations such as the above Ghartok Triolith which depicts the hand of Mephala, the [Imperial Triolith](https://en.uesp.net/wiki/File:MW-cover-Morrowind_Box_Art.jpg) which features the Seal of Akatosh, and more recently, the [Nerevarine Triolith](https://media.moddb.com/images/articles/1/154/153713/2ik4pc5.jpg.png) depicting [Moon-and-Star](https://en.uesp.net/wiki/Lore:Moon-and-Star) at it's center.

## About the Trigrammaton

The word "ALMSIVI" is a *portmanteau* of the three individual names of the Tribunal godhead. However, the letters themselves are merely a roman rendering of the phonetic pronunciation of the Daedric glyphs, <span style="font-family:Daedric; color:red">ASV</Span>, *ASV*.

The word itself, literally unpronounceable by Dunmer, comes from [Ehlnofex](https://en.uesp.net/wiki/Lore:Ehlnofex_Languages). The [blended form](http://www.gamesas.com/understanding-the-sermons-t346774.html#p4640584:~:text=is%20ehlnofex%20for) is simply the closest one can come to pronouncing a word in a divine language. Spelling each letter case as capital is a way of culturally denoting that the word *itself* is holy when uttered.

###### In Daedric script, holy words are written in red. Specify the color in the span tag like so:
```html
<span style="font-family:Daedric; color:red">ASV</Span>
```

Based on the textual examples that I have seen, it would appear that red is the honorific color that represents holy words or names when writing in the Daedric script. As a matter of propriety, I try to only highlight the names of the most renowned figures and only where it seems contextually appropriate to do so. When romanizing, it is best to stick to the system of [reverential capitalization](https://en.wikipedia.org/wiki/Reverential_capitalization), however your interpretation will probably vary.

|ALMSIVI in every hour|
|:-:|
|ASV gher alni telsan|
|<span style="font-family:Daedric;"> <span style="color:red">ASV</Span> gher alni telsan</span>|

The fact that [words in Ehlnofex](https://en.uesp.net/wiki/Lore:CHIM) are fluid would support the custom that surrounds the Trigrammaton, concerning the centering of the Daedric character for the respective deity in their regions of worship.

For example, in the Holy City of Vivec, ALMSIVI is rendered, \"<span style="font-family:Daedric; color:red">AVS</Span>,\" [*AVS*](https://en.uesp.net/wiki/Morrowind:Tribunal_Temple), while in the Holy Capitol of Mournhold, it is rendered \"<span style="font-family:Daedric; color:red">SAV</Span>,\" [*SAV*](https://en.uesp.net/wiki/Lore:Daedric_Alphabet#Morrowind). In all places, it is still pronounced the same.

For a better understanding of the symbolic thought influencing this mysterious three letter word, see the [Tetragrammaton](https://en.wikipedia.org/wiki/Tetragrammaton) and the article on Ehlnofex.

---

## Further Reading

It seems relevant to have a look at [Earthsea](https://en.wikipedia.org/wiki/A_Wizard_of_Earthsea) and it's use of [*Rumpelstiltskin theory*](https://sjaakvandergeest.socsci.uva.nl/pdf/anthropology_and_literature/rumpelskin.pdf) or the idea that [*True* words](https://en.wikipedia.org/wiki/True_name) may have power. There seems to be a [similar current](https://www.imperial-library.info/content/posts-kirkbride-undated#node-8393:~:text=On%20Vivec%20and%20Morrowind) present in many Tamrielic religions and languages.

The Tribunal Faith and it's influence on Dunmer culture cannot be understated. The Temple has what can be considered an "[open canon](https://en.wikipedia.org/wiki/Biblical_canon#:~:text=In%20contrast%2C%20an%20%22open%20canon,their%20respective%20faiths%20and%20denominations.)" of scriptures which have evolved over time and region to include many texts. Some of the most seminal works include:
- [The Homilies of Blessed Almalexia](https://en.uesp.net/wiki/Lore:Homilies_of_Blessed_Almalexia) (<span style="font-family:Daedric">as malyudhardii</span>, As Malyudhardii, lit., "the homilies")
- [The Truth in Sequence](https://en.uesp.net/wiki/Lore:The_Truth_in_Sequence) (<span style="font-family:Daedric">as leyrihn</span>, As Leyrihn, lit., "the sequence")
- [The 36 Lessons of Vivec](https://en.uesp.net/wiki/Lore:The_36_Lessons_of_Vivec) (<span style="font-family:Daedric">as shoreshiik</span>, *As Shoreshiik*, lit., "the lessons" )

Collected and canonized texts are often reflective of the local temples and their communities.

To learn more about Dunmer religion, have a look at the following resources:

- [Fellowship of the Temple](https://en.uesp.net/wiki/Lore:Fellowship_of_the_Temple) (<span style="font-family:Daedric">daeljuha am daenthi</span>, *Daeljuha am Daenthi*), an introductory pamphlet on The Tribunal Temple (<span style="font-family:Daedric">as daenthi</span>, *As Daenthi*, lit., "the temple")
- [Organization of the Temple](https://www.reddit.com/r/teslore/comments/1on7gw/a_short_introduction_to_the_tribunal_temple/)
- [What is the Religious History of the Dunmer?](https://writteninuncertainty.com/podcast/dunmer-religion/)
- [Dunmer Beliefs and Customs of the Dead](https://en.uesp.net/wiki/Lore:Death#Dunmer_Beliefs_and_Customs)
  - [The Doors of the Spirit](https://en.uesp.net/wiki/Lore:The_Doors_of_the_Spirit)
- [The New Whirling School Commentary](https://www.newwhirlingschool.com), A major work-in-progress commentary on the 36 Lessons
  - [Intro to Terminology](https://www.newwhirlingschool.com/intro.php)
  - [Exploratory Essays](https://www.newwhirlingschool.com/intro.php#essays)
- [Jerome's Short Commentary](https://jeromeiv-blog.tumblr.com/post/19934786003/sermon-1-of-36-lessons-of-vivec-dissection), incomplete but venerably covers the first six chapters of the 36 Lessons

Finally, some further essays and topics relating to Morrowind and religion:

- [Religion in Computer Games](http://kau.diva-portal.org/smash/get/diva2:508317/FULLTEXT01.pdf), an essay by Jon Ode that explores the forms and implications of religion in games using Morrowind as the example
- [A Treatise on the Subject of Daedra Worship](https://luke-a-fytch.itch.io/a-treatise-on-the-subject-of-daedra-worship), an essay by Luke A. Fytch that details the emergence of a new form of pop-culture paganism
- [Prophecy, Pre-Destination, and Free-form Gameplay](https://heiup.uni-heidelberg.de/journals/index.php/religions/article/view/18512/12320), an essay by Angus Slater from the Heidelberg Journal of Religions on the Internet, Vol. 7, pg. 161 that explores the Nerevarine Prophecy's affect on gameplay

|"ALMSIVI", fresco by [Tyddyner](https://tyddyner.tumblr.com/) \[[1](https://tyddyner.tumblr.com/post/127475780830/almalexia-godess-queen-of-morrowind-warden-lover), [2](https://tyddyner.tumblr.com/post/127579542465/sotha-sil-mystery-god-of-morrowind-the-last-one), [3](https://tyddyner.tumblr.com/post/127640108900/vivec-vehk-and-vehk-god-thief-and-god-poet)\]|
|:-:|
|![Tribunal](assets/images/fresco-256.png?raw=true "Tribunal")|

---

## Publishing Your Work

It's easy to convert Markdown to PDF. With your viewer of choice, you can use your operating system's *Print to PDF* feature.

It's also very easy to convert formats using [pandoc](https://pandoc.org/):

```
pandoc example.md --standalone --output example.pdf
```

## Final Words

I'm no language expert and there's plenty I have not accounted for. The irreverent, more clinical emphasis of Telvanni culture has had an affect on the language. [Architecture plays a key role](https://ajmchugh.wordpress.com/2019/06/19/how-vivec-city-reinforces-morrowinds-politics/) in culture as well and it varies wildly between region. There is also something to be said of the similarities between the Dunmer and the [pre-Roman Celts](https://en.wikipedia.org/wiki/Insular_Celts).

There is a lot to be observed and discovered about Morrowind and I am barely scratching the surface as I write down what little I've learned. I don't intend for this to act as a primary source, but a quick point of reference.

Now go have fun, get into the spirit of things, and don't take anything too seriously!

---

<center>
<span style="font-family:Daedric">as dimihn am as edur <span style="color:red">ASV</span></span>
</center>

---

