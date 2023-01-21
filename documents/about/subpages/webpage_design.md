
---

<!--- Local CSS Font Loading -->

<style>
@font-face {
    font-family: HayghinDaedric;
    src: url('../../assets/fonts/ttf/HayghinDaedric.ttf') format('truetype');
    font-weight: medium;
    font-style: normal;
}
</style>

<!--- Jekyll Page Links -->

<center>
<a href="../../index.html">Home</a>
&emsp;&nabla;&emsp;
<a href="../index.html">About</a>
&emsp;&nabla;&emsp;
<a href="../../archive/index.html">Archive</a>
&emsp;&nabla;&emsp;
<a href="../../quintessence/index.html">Quintessence</a>
</center>

<!--- Markdown Body Below: -->

---

Markdown is a plain-text language that makes writing formatted documents very easy. It's also possible to call custom fonts in Markdown using in-line HTML. By incorporating one of the available online dialects, it's very easy to quickly produce shareable documents in Dunmeris (<span style="font-family:HayghinDaedric">dunmeris</span>), the language of the people of Morrowind.

[Try the template!][1]

Some translation examples:

|Three blessings, sera|Walk with virtue|Why walk when you can ride?|
|:-:|:-:|:-:|
|Cahn'shoksunaa sera|Khosi enhi julopum|Ju'it khosi ku'elm ohn duhnanich?
|<span style="font-family:HayghinDaedric">cahn'shoksunaa sera</span>|<span style="font-family:HayghinDaedric">khosi enhi julopum</span>|<span style="font-family:HayghinDaedric">ju'it khosi ku'elm ohn duhnanich?</span>

[1]: https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0

## Quick Info:

Want to jump right in to creating and translating your own manuscripts? Here's all you need:

- [Markdown Syntax][2]
- [Hayghin Daedric font][3] (based on [Ayembedt][4]\)
- [Casual Dunmeris][5]
- [GitHub Template][6]

[2]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
[3]: https://github.com/mmillar-bolis/HayghinDaedricFont/releases/
[4]: https://github.com/georgd/OpenMW-Fonts
[5]: https://casualscrolls.fandom.com/wiki/Dunmeri_language
[6]: https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0

---

## Further Background

If you are unfamiliar with [John Gruber][7] and [Aaron Swartz][8]'s Markdown language, [have a look at it][9].

Markdown is a text formatting language that translates to strict HTML. The central focus and reason for the language is to store source text in the most human readable fashion possible but still be able to render it with formatted HTML.

Aside from the [Reference Specification][10], there are other slightly different dialects as well such as, [GitHub Flavored Markdown][11] and [Pandoc Markdown][12].

However, all you really need to get started is something like [Adam Pritchard's Markdown Cheatsheet][13].

[7]: https://daringfireball.net/projects/markdown/
[8]: https://en.wikipedia.org/wiki/Aaron_Swartz
[9]: https://www.markdownguide.org/getting-started/
[10]: https://daringfireball.net/projects/markdown/
[11]: https://github.github.com/gfm/
[12]: https://pandoc.org/MANUAL.html#pandocs-markdown
[13]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

---

## ToolKit

Markdown files are plain-text files with the extension, `.md`. As with HTML, any text editor, such as Notepad and TextEdit, can be used to create and edit markdown files. However, choosing a text editor that supports [syntax highlighting][14] will make things significantly easier to read.

In addition to a text editor, one will also need a way to view rendered markdown. A few viewer applications exist as well as some browser plugins. However, many major code editors also incorporate some form of markdown viewer these days as well.

- A Text Editor:
  - __Any plain-text editor, really!__
  - [Notepad2-mod][15]
  - [Micro][16]
  - [GVim][17]

- A Markdown Viewer:
  - [MdView][18]
  - [Markdown Viewer][19] browser extension
  - [mdless][20] command-line tool
  - [glow][21] command-line tool

- Viewer/Editor:
  - [Visual Studio Code][22]
  - [Notepad++][23] with [MarkdownViewer++][24]
  - [Atom][25] with [Markdown Preview][26]
  - [Typora][27]

[14]: https://en.wikipedia.org/wiki/Syntax_highlighting
[15]: https://xhmikosr.github.io/notepad2-mod/
[16]: https://micro-editor.github.io/
[17]: https://www.vim.org/download.php#pc
[18]: https://github.com/c3er/mdview
[19]: https://github.com/simov/markdown-viewer
[20]: https://brettterpstra.com/projects/mdless/
[21]: https://github.com/charmbracelet/glow
[22]: https://code.visualstudio.com/Download
[23]: https://notepad-plus-plus.org/
[24]: https://github.com/nea/MarkdownViewerPlusPlus/releases
[25]: https://atom.io/
[26]: https://github.com/atom/markdown-preview
[27]: https://typora.io/

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

Optionally, if your markdown viewer does not allow for loading external fonts, you can convert the font to embeddable text using [Base64][28] and then insert that into your tag. Below I have changed the source to load text data from the URL path where *<BASE64_TEXT_CONTENTS>* is the ASCII conversion of a TrueType font:

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
<span style="font-family:HayghinDaedric">makhel fahraj</span>
```

All one really needs to get started is this handy [GitHub template][29]! The documents within already contain this style element, one with the font embedded and the other with a reference to the loose `.ttf` font. They are ready for editing or viewing from a local markdown renderer, provided the font folder is kept with loose one.

[28]: https://en.wikipedia.org/wiki/Base64
[29]: https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0

---

## About This Font

|The Thrice-sealed House withstands the Storm|
|:-:|
|As cahnarurhili'ag'thil yalig as malroua|
|<span style="font-family:HayghinDaedric">as cahnarurhili'ag'thil yalig as malroua</span>|

I have created a custom font called *hayghin* or simple Daedric. The base designs are borrowed from the [Ayembedt font][30] created by Georg Duffner for [OpenMW][31]. I have resized the glyphs and added some punctuation marks. It's recompiled into a smaller sized TrueType font using [FontForge][32].

Both the compiled `.ttf` and the Base64 rendering, as well as it's source code with the modifications are available in the assets directory of the GitHub repo.

[30]: https://github.com/georgd/OpenMW-Fonts
[31]: https://openmw.org
[32]: https://fontforge.org/en-US/downloads/

---

## Language Guidelines Used

For starters, there is the excellent [Calligraphy Manual][33], by Llevndryn Sershilavu. It explores the complex writing system of the Dunmer and the Daedric glyphs.

The language dialect I have chosen for most of my translations is the continually expanding [Casual Dunmeris][34], so named because of the wiki it comes from: [Casual Scrolls][35]. The forum's founder and the original publisher of the language, is [Matthew Knight][36], now a Catholic priest.

There is a lot of activity surrounding this dialect and it seems very well developed. When translating cultural adages of Morrowind, I find that Casual Dunmeris rolls with off the tongue rather well.

It is unclear (to me at least) who specifically originally collaborated on the language, or if it was mostly the work of Knight, but it appears that around 2011, a framework was designed for the members of the [original party][37] of a [PbP][38] Elder Scrolls campaign that was being recorded on the Casual Scrolls wiki.

[33]: https://forums.elderscrollsonline.com/en/discussion/265828/calligraphy-manual-daedric-alphabet-in-dunmeris
[34]: https://casualscrolls.fandom.com/wiki/Dunmeri_language
[35]: https://casualscrolls.fandom.com/
[36]: https://casualscrolls.fandom.com/wiki/User:Mknightretke
[37]: https://casualscrolls.fandom.com/wiki/Casual_Elder_Scrolls_Wiki#Characters
[39]: https://en.wikipedia.org/wiki/Play-by-post_role-playing_game

|Learn by serving|
|:-:|
|Viya ru yilakam|
|<span style="font-family:HayghinDaedric">viya ru yilakam</span>|


Following the [lineage of Ehlnofex languages][40], one can see that Dunmeris is derived from Aldmeris. If anyone has further interest, for an additional translation guide, resource, and inspiration, there is a fascinating project to [document Aldmeris][41].

There are other dialects of Dunmeris as well. [Hrafnir II][42] documents [Ald Redoranis][43], a notable fourth era dialect. [Tarhiel][44] writes about an Ashlander dialect called [Velothi][45]. Isfendil is recording the southern dialect of [Veki][46] Dunmeris.

Since Casual Dunmeris is ultimately still developing, I have also taken to inventing words as the need arises, based on already available nouns and verbs that I smash together. As a last resort, I might adapt an Aldmeri word if one exists.

As the culture is *very* high-context, it seems proper that much of the language information appear implicit. Following the guidelines from the Casual Wiki, on dumbing down the sentence complexity before translating into Dunmeris, as well as examples like the [Words of the Wind][47] and [The Book of Dawn and Dusk][48], I have taken subtle liberties with some phrases to make them appear more like prayers or mantras. For example, as a dunmer [*amen*][49], I modified the below common scriptural ending phrase. Other places, people simplify sentences to fit the currently available set of words, producing some very creative results.

| The ending of the words is ALMSIVI | The forceful expression of will gives true honor to the Ancestors |
|:----------------------------------:|:---:|
|  The ending of the words: ALMSIVI  | The strong speech of will gives true respect to the Ancestors |
|    As dimihn am as lehjii, ASV     | As jubu gahrudi am khamir jikhig neen lorkor de Card |
| <span style="font-family:HayghinDaedric">as dimihn am as lehjii, <span style="color:red">ASV</span> | <span style="font-family:HayghinDaedric">As jubu gahrudi am khamir jikhig neen lorkor de card</span> |

[40]: https://en.uesp.net/wiki/Lore:Ehlnofex_Languages
[41]: https://tes-sandbox.fandom.com/wiki/Aldmeris_(Language)
[42]: https://www.imperial-library.info/users/hrafnir-ii
[43]: https://www.imperial-library.info/content/hrafnirs-languages-nordic#Dunmeris
[44]: https://archiveofourown.org/users/tarhiel
[45]: https://chameleonspell.tumblr.com/post/147090784528/ashlander-language-1-phonemes
[46]: https://conworkshop.com/view_language.php?l=DUNMR
[47]: https://en.uesp.net/wiki/Lore:Words_of_the_Wind
[48]: https://en.uesp.net/wiki/Lore:The_Book_of_Dawn_and_Dusk
[49]: https://en.wikipedia.org/wiki/Amen

---

## Language and Religion

The triple-diety at the center of the Tribunal Temple faith (<span style="font-family:HayghinDaedric">as daenthi</span>, *As Daenthi*, lit., "the temple") is known as "ALMSIVI."  The title is a *portmanteau* of the three individual names of the [Tribunal godhead][50]. However, the letters themselves are merely a westernized rendering of the phonetic pronunciation of the Daedric glyphs, <span style="font-family:HayghinDaedric; color:red">ASV</Span>, [*A-S-V*][51].

The word itself, though technically unpronounceable, comes from the Ehlnofex language. The [blended form][52], *almsivi*, is simply the closest one can come to pronouncing a word in a divine language. Spelling each letter case as capital is a form of [reverential capitalization][53], a way of denoting that the word *itself* is holy or an honorific title.

|ALMSIVI in every hour|
|:-:|
|ASV gher alni telsan|
|<span style="font-family:HayghinDaedric;"> <span style="color:red">ASV</Span> gher alni telsan</span>|

[Words in Ehlnofex][54] are represented by [sigils][55] that move with fluidity and do not necessarily follow a left-to-right order that the Daedric script does. It is often the case that the Trigrammaton is written in the *neutral* order, the way that most Dunmer pronounce it.

In Daedric script, holy words are sometimes written in red. Specify the color in the span tag like so:

```html
<span style="font-family:HayghinDaedric; color:red">ASV</Span>
```

Based on [some][56] of the [examples][57] that I have seen, it would appear that red is an honorific color that may represent holy names, powerful words, or strong emphasis, when writing in the Daedric script. As a matter of propriety, I try to highlight sparingly and only where it seems contextually appropriate to do so.

[50]: https://en.uesp.net/wiki/Lore:Gods_T#Tribunal
[51]: https://en.uesp.net/wiki/Lore:The_36_Lessons_of_Vivec#Sermon_One
[52]: http://www.gamesas.com/understanding-the-sermons-t346774.html#p4640584:~:text=is%20ehlnofex%20for
[53]: https://en.wikipedia.org/wiki/Reverential_capitalization
[54]: https://en.uesp.net/wiki/Lore:CHIM
[55]: https://en.wikipedia.org/wiki/Sigil
[56]: https://www.etsy.com/listing/223690247/the-tribunal-gods-of-morrowind-print
[57]: https://en.uesp.net/wiki/Category:Morrowind-Banner_Images

---

## Publishing Your Work

It's easy to convert Markdown to PDF. With your viewer of choice, you can use your operating system's *Print to PDF* feature.

It's also very easy to convert formats using [pandoc][58]:

```
pandoc example.md --standalone --output example.pdf
```

Finally, GitHub has a [guide to publishing pages][59] if you too would like to take your markdown and turn it into a website like this one.

[58]: https://pandoc.org/
[59]: https://guides.github.com/features/pages/

---

## Final Words

I'm no language expert and there's plenty I have not accounted for. The irreverent, more clinical emphasis of Telvanni subculture has had an affect on the language. [Architecture plays a key role][60] in Dunmer expression as well and it varies wildly between regions. There is also the influence of [House Dres][61] and the practice of slavery throughout Morrowind, as well as it's [eventual ban][62].

|The Twin-lamps light the way to freedom|
|:-:|
|As asc'aaf sincag as manidi de julgham|
|<span style="font-family:HayghinDaedric">as asc'aaf sincag as manidi de julgham</span>|

The series can [trace it's roots][63] to [RuneQuest][64], set in the world of [Glorantha][65]. There is something to be said of the similarities between the Dunmer and the [pre-Roman Celts][66] as well.

My point is that there is a lot to be observed and discovered about Morrowind and I am barely scratching the surface as I write down what little I've learned. I don't intend for this to act as any primary source, just a quick point of reference.

Now go have fun, get into the spirit of things, and don't take anything too seriously!

[60]: https://ajmchugh.wordpress.com/2019/06/19/how-vivec-city-reinforces-morrowinds-politics/
[61]: https://en.uesp.net/wiki/Lore:House_Dres
[62]: https://www.imperial-library.info/content/pocket-guide-empire-third-edition-temple-morrowind#node-1966:~:text=outlawed%20slavery%20throughout%20Morrowind
[63]: https://rpg.stackexchange.com/questions/89399/is-morrowind-based-on-a-tabletop-rpg/89416
[64]: https://en.wikipedia.org/wiki/RuneQuest
[65]: https://en.wikipedia.org/wiki/Glorantha
[66]: https://en.wikipedia.org/wiki/Insular_Celts

---
