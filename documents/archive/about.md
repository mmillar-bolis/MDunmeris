
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
<a href="about.html">About</a>
&emsp;&nabla;&emsp;
<a href="index.html">Archive</a>
&emsp;&nabla;&emsp;
<a href="../quintessence/index.html">Quintessence</a>
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
Want to skip the article and jump right in to creating and translating manuscripts? Here's all you need:

- [Markdown Syntax][2]
- [Hayghin Daedric font][3] (based on [Ayembedt][4]\)
- [Casual Dunmeris][5]

[2]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
[3]: https://github.com/mmillar-bolis/HayghinDaedricFont/releases/
[4]: https://github.com/georgd/OpenMW-Fonts
[5]: https://casualscrolls.fandom.com/wiki/Dunmeri_language

---

## Further Background

If you are unfamiliar with [John Gruber][6] and [Aaron Swartz][7]'s Markdown language, [have a look at it][8].

Markdown is a text formatting language that translates to strict HTML. The central focus and reason for the language is to store source text in the most human readable fashion possible but still be able to render it with formatted HTML.

Aside from the [Reference Specification][9], there are other slightly different dialects as well such as, [GitHub Flavored Markdown][10] and [Pandoc Markdown][11].

However, all you really need to get started is something like [Adam Pritchard's Markdown Cheatsheet][12].

[6]: https://daringfireball.net/projects/markdown/
[7]: https://en.wikipedia.org/wiki/Aaron_Swartz
[8]: https://www.markdownguide.org/getting-started/
[9]: https://daringfireball.net/projects/markdown/
[10]: https://github.github.com/gfm/
[11]: https://pandoc.org/MANUAL.html#pandocs-markdown
[12]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

---

## ToolKit

Markdown files are plain-text files with the extension, `.md`. As with HTML, any text editor, such as Notepad and TextEdit, can be used to create and edit markdown files. However, choosing a text editor that supports [syntax highlighting][13] will make things significantly easier to read.

In addition to a text editor, one will also need a way to view rendered markdown. A few viewer applications exist as well as some browser plugins. However, many major code editors also incorporate some form of markdown viewer these days as well.

- A Text Editor:
  - __Any plain-text editor, really!__
  - [Notepad2-mod][14]
  - [Micro][15]
  - [GVim][16]

- A Markdown Viewer:
  - [MdView][17]
  - [Markdown Viewer][18] browser extension
  - [mdless][19] command-line tool
  - [glow][20] command-line tool

- Viewer/Editor:
  - [Visual Studio Code][21]
  - [Notepad++][22] with [MarkdownViewer++][23]
  - [Atom][24] with [Markdown Preview][25]
  - [Typora][26]

[13]: https://en.wikipedia.org/wiki/Syntax_highlighting
[14]: https://xhmikosr.github.io/notepad2-mod/
[15]: https://micro-editor.github.io/
[16]: https://www.vim.org/download.php#pc
[17]: https://github.com/c3er/mdview
[18]: https://github.com/simov/markdown-viewer
[19]: https://brettterpstra.com/projects/mdless/
[20]: https://github.com/charmbracelet/glow
[21]: https://code.visualstudio.com/Download
[22]: https://notepad-plus-plus.org/
[23]: https://github.com/nea/MarkdownViewerPlusPlus/releases
[24]: https://atom.io/
[25]: https://github.com/atom/markdown-preview
[26]: https://typora.io/

---

## Fonts in Markdown

Knowing that Markdown files are translated into HTML, one can actually embed HTML directly into a document for edge-case needs. To do so goes a bit against the ethos behind the language, but it does reasonably introduces a way to rapid prototype tricky designs when Pandoc is not available or you don't have template files to surround your markdown yet, or you don't want to install fonts to your system.

Adding a style tag to the beginning of your document will allow for some CSS to import a font. Below is an example of an HTML style tag with embedded CSS that declares a font:

```html
<style>
@font-face {
    font-family: Daedric;
    src: url("/path/to/HayghinDaedric.ttf") format('truetype');
    font-weight: medium;
    font-style: normal;
}
</style>
```

Optionally, if your markdown viewer does not allow for loading external fonts, you can convert the font to embeddable text using [Base64][27] and then insert that into your tag. Below I have changed the source to load text data from the URL path where *<BASE64_TEXT_CONTENTS>* is the plain text conversion of a TrueType font:

```html
    src: url(data:font/truetype;charset=utf-8;base64,<BASE64_TEXT_CONTENTS>) format('truetype');
```

This will allow you to distribute a single, flat markdown file with fonts, similar to a `.pdf`. However, it is important to know that embedding fonts produces *large* text files, and these can be difficult to work with if not maintained. (For this project, I am only importing *loose* fonts.) In some rare cases, antiviral programs might regard embedded Base64 as suspicious.

Finally, you can render text in your Markdown body by wrapping it with a span tag that specifies the font by it's internal name (not filename):

```html
<span style="font-family:HayghinDaedric">makhel fahraj</span>
```

All one really needs to get started is this handy [GitHub template][28]! The documents within already contain this style element, one with the font embedded and the other with a reference to the loose `.ttf` font. They are ready for editing or viewing from a local markdown renderer, provided the font folder is kept with loose one.

[27]: https://en.wikipedia.org/wiki/Base64
[28]: https://github.com/mmillar-bolis/MDunmeris/releases/tag/0.0.0.0

---

## About This Font

|The Thrice-sealed House withstands the Storm|
|:-:|
|As cahnarurhili'ag'thil yalig as malroua|
|<span style="font-family:HayghinDaedric">as cahnarurhili'ag'thil yalig as malroua</span>|

I have created a custom font called *hayghin* or simple Daedric. The base designs are borrowed from the [Ayembedt font][29] created by Georg Duffner for [OpenMW][30]. I have resized the glyphs and added some punctuation marks. It's recompiled into a smaller sized TrueType font using [FontForge][31].

Both the compiled `.ttf` and the Base64 rendering, as well as it's source code with the modifications are available in the assets directory of the GitHub repo.

[29]: https://github.com/georgd/OpenMW-Fonts
[30]: https://openmw.org
[31]: https://fontforge.org/en-US/downloads/

---

## Language Guidelines Used

For starters, there is the excellent [Calligraphy Manual][32], by Llevndryn Sershilavu. It explores the complex writing system of the Dunmer and the Daedric glyphs.

The language dialect I have chosen for most of my translations is the continually expanding [Casual Dunmeris][33], so named because of the wiki it comes from: [Casual Scrolls][34]. The forum's founder and the original publisher of the language, is [Matthew Knight][35], now a Catholic priest.

There is a lot of activity surrounding this dialect and it seems very well developed. When translating cultural adages of Morrowind, I find that Casual Dunmeris rolls with off the tongue rather well.

It is unclear (to me at least) who specifically originally collaborated on the language, or if it was mostly the work of Knight, but it appears that around 2011, a framework was designed for the members of the [original party][36] of a [PbP][37] Elder Scrolls campaign that was being recorded on the Casual Scrolls wiki.

[32]: https://forums.elderscrollsonline.com/en/discussion/265828/calligraphy-manual-daedric-alphabet-in-dunmeris
[33]: https://casualscrolls.fandom.com/wiki/Dunmeri_language
[34]: https://casualscrolls.fandom.com/
[35]: https://casualscrolls.fandom.com/wiki/User:Mknightretke
[36]: https://casualscrolls.fandom.com/wiki/Casual_Elder_Scrolls_Wiki#Characters
[37]: https://en.wikipedia.org/wiki/Play-by-post_role-playing_game

|Learn by serving|
|:-:|
|Viya ru yilakam|
|<span style="font-family:HayghinDaedric">viya ru yilakam</span>|


Following the [lineage of Ehlnofex languages](https://en.uesp.net/wiki/Lore:Ehlnofex_Languages), one can see that Dunmeris is derived from Aldmeris. If anyone has further interest, for an additional translation guide, resource, and inspiration, there is a fascinating project to [document Aldmeris](https://tes-sandbox.fandom.com/wiki/Aldmeris_(Language)).

There are other dialects of Dunmeris as well. [Hrafnir II](https://www.imperial-library.info/users/hrafnir-ii) documents [Ald Redoranis](https://www.imperial-library.info/content/hrafnirs-languages-nordic#Dunmeris), a notable fourth era dialect. [Tarhiel](https://archiveofourown.org/users/tarhiel) writes about an Ashlander dialect called [Velothi](https://chameleonspell.tumblr.com/post/147090784528/ashlander-language-1-phonemes). Isfendil is recording the southern dialect of [Veki](https://conworkshop.com/view_language.php?l=DUNMR) Dunmeris.

Since Casual Dunmeris is ultimately still developing, I have also taken to inventing words as the need arises, based on already available nouns and verbs that I smash together. As a last resort, I might adapt an Aldmeri word if one exists.

As the culture is *very* high-context, it seems proper that much of the language information appear implicit. Following the guidelines from the Casual Wiki, on dumbing down the sentence complexity before translating into Dunmeris, as well as examples like the [Words of the Wind](https://en.uesp.net/wiki/Lore:Words_of_the_Wind) and [The Book of Dawn and Dusk](https://en.uesp.net/wiki/Lore:The_Book_of_Dawn_and_Dusk), I have taken subtle liberties with some phrases to make them appear more like prayers or mantras. For example, as a dunmer [*amen*](https://en.wikipedia.org/wiki/Amen), I modified the common scriptural ending phrase. Other places, people simplify sentences to fit the currently available set of words, producing some very creative results.

| The ending of the words is ALMSIVI | The forceful expression of will gives true honor to the Ancestors |
|:----------------------------------:|:---:|
|  The ending of the words: ALMSIVI  | The strong speech of will gives true respect to the Ancestors |
|    As dimihn am as lehjii, ASV     | As jubu gahrudi am khamir jikhig neen lorkor de Card |
| <span style="font-family:HayghinDaedric">as dimihn am as lehjii, <span style="color:red">ASV</span> | <span style="font-family:HayghinDaedric">As jubu gahrudi am khamir jikhig neen lorkor de card</span> |

---

## Religion and Morrowind

| Ghartok Trigon |
|:--------------:|
|![Trigon](assets/images/symbols/trigon_ghartok-256.png?raw=true "Trigon")|

---

## About the Trigonic Symbol

The central religious symbol of the Tribunal Temple faith (<span style="font-family:HayghinDaedric">as daenthi</span>, *As Daenthi*, lit., "the temple") is the depiction of the [Trigon](https://d2skuhm0vrry40.cloudfront.net/2019/articles/2019-05-22-11-21/Lessons4.jpg/EG11/resize/690x-1/quality/75/format/jpg). A [representation](https://en.uesp.net/wiki/File:SR-book-Oghma_Infinium_2.png) of the [Enantiomorph](https://elderscrolls.fandom.com/wiki/Enantiomorph), this symbol is an inverse triangle with Daedric glyphs in each corner, which if read clockwise, spell *ASV*. However, it can also be common to see variants of this symbol such as the above [Ghartok Trigon](https://www.imperial-library.info/content/forum-archives-michael-kirkbride#node-2865:~:text=What%20does%20%22GHARTOK%22%20mean%3F) which depicts the [Hand of Mephala](https://en.uesp.net/wiki/Lore:36_Lessons_of_Vivec,_Sermon_11#genWhiteText:~:text=black%20hands) at the center, or the [Imperial Trigon](https://en.uesp.net/wiki/File:MW-cover-Morrowind_Box_Art.jpg) which features the [Seal of Akatosh](https://en.uesp.net/wiki/Lore:Akavir), and more recently, the [Nerevarine Trigon](https://media.moddb.com/images/articles/1/154/153713/2ik4pc5.jpg.png) depicting the [Moon-and-Star](https://en.uesp.net/wiki/Lore:Moon-and-Star) at it's center.

---

## About the Trigrammaton

The word "ALMSIVI" is a *portmanteau* of the three individual names of the [Tribunal godhead](https://en.uesp.net/wiki/Lore:Gods_T#Tribunal). However, the letters themselves are merely a roman rendering of the phonetic pronunciation of the Daedric glyphs, <span style="font-family:HayghinDaedric; color:red">ASV</Span>, [*A-S-V*](https://en.uesp.net/wiki/Lore:The_36_Lessons_of_Vivec#Sermon_One).

The word itself, technically unpronounceable, comes from [Ehlnofex](https://en.uesp.net/wiki/Lore:Ehlnofex_Languages). The [blended form](http://www.gamesas.com/understanding-the-sermons-t346774.html#p4640584:~:text=is%20ehlnofex%20for), *almsivi*, is simply the closest one can come to pronouncing a word in a divine language. Spelling each letter case as capital is a form of [reverential capitalization](https://en.wikipedia.org/wiki/Reverential_capitalization), a way of denoting that the word *itself* is holy or an honorific title.

|ALMSIVI in every hour|
|:-:|
|ASV gher alni telsan|
|<span style="font-family:HayghinDaedric;"> <span style="color:red">ASV</Span> gher alni telsan</span>|

[Words in Ehlnofex](https://en.uesp.net/wiki/Lore:CHIM) are represented by [sigils](https://en.wikipedia.org/wiki/Sigil) that move with fluidity and do not necessarily follow a left-to-right order that the Daedric script does. It is often the case that the Trigrammaton is written in the *neutral* order, the way that most Dunmer pronounce it. However, there are strong cultural customs surrounding the arrangement of these characters. In particular geographic locations, it can be observed that the center glyph points to a particular deity of devotion. Generally, the arrangement follows a pattern of rotating the order of glyphs on the Trigon such that the favored deity is on the bottom point, then collapsing those characters into a single line.

For example, in the city of Vivec, ALMSIVI is rendered, \"<span style="font-family:HayghinDaedric; color:red">AVS</Span>,\" [*A-V-S*](https://en.uesp.net/wiki/Morrowind:Tribunal_Temple), while in the capitol of Mournhold, it is rendered \"<span style="font-family:HayghinDaedric; color:red">SAV</Span>,\" [*S-A-V*](https://en.uesp.net/wiki/Lore:Daedric_Alphabet#Morrowind:~:text=In%20Mournhold%2C%20Almalexia%20gets%20top%20billing). In all places, it is still pronounced the same.

For a better understanding of the symbolic thought this mysterious three letter word, see the [Tetragrammaton](https://en.wikipedia.org/wiki/Tetragrammaton). In addition, many draw allusions to the Christian metaphor of [Alpha and Omega](https://en.wikipedia.org/wiki/Alpha_and_Omega). However, that metaphor is derived from an earlier one, the Hebrew word [emet](https://en.wikipedia.org/wiki/Alpha_and_Omega#Judaism) which means *truth* and is spelled with the beginning, middle, and ending letters of the [Hebrew alphabet](https://en.wikipedia.org/wiki/Hebrew_alphabet), *alef*, *mem*, and *tav*.

But why write it as *almsivi*? Aside from the fact that it rolls of the tongue better and is a more obvious mashup of the three names of the gods to English readers, there is a significant [numerological](https://en.wikipedia.org/wiki/Numerology) aspect to adding extra letters bringing it to [seven](https://en.wikipedia.org/wiki/Symbolism_of_the_number_7) in length. The number occurs in [other](https://en.uesp.net/wiki/Lore:The_Seven_Visions) [areas](https://en.uesp.net/wiki/Lore:The_Seven_Curses) of [dunmer religion](https://en.uesp.net/wiki/Lore:The_Pilgrim%27s_Path). This also gives the English rendering of the word the same length in letters as the amount of sylables found in the Ehlnofex phrase from which it is derived, [AYEM AE SEHTI AE VEHK](https://en.uesp.net/wiki/Morrowind:36_Lessons_of_Vivec,_Sermon_1#genWhiteText:~:text=AYEM%20AE%20SEHTI%20AE%20VEHK), or *A is S is V*. It's the sum of 3 + 4, considered in many religious cultures to represent, respectively, [sacred and material numbers](https://www.jstor.org/stable/658538). This further fits within the Dunmer model of three [Anticipations](https://en.uesp.net/wiki/Lore:The_Anticipations) above four members of the [House of Troubles](https://en.uesp.net/wiki/Lore:The_House_of_Troubles).

Seven is also a prime number input for calculating [perfect numbers](https://en.wikipedia.org/wiki/Perfect_number), which break down into a sum of positive [factors](https://en.wikipedia.org/wiki/Factorization), not including the number itself. Here's a simplified example, using the smallest perfect number, `6`:

| Equation | Result |
|:--------:|:------:|
|   1 * 6  |   6    |
|   2 * 3  |   6    |
|   3 * 2  |   6    |
|   6 * 1  |   6    |

So in this example, the perfect number `6` would then be derived from adding `1`,`2`, and `3`:

|  Equation | Result |
|:---------:|:------:|
| 1 + 2 + 3 |   6    |

The philosopher and mathematician [Euclid](https://en.wikipedia.org/wiki/Euclid) is credited with coming up with a [theorem](https://en.wikipedia.org/wiki/Euclid%E2%80%93Euler_theorem) that perfect numbers must be derived from primes following the equation 2&#8319;&#8315;&sup1;(2&#8319; - 1) where &#8319; is a prime number. So for &#8319; = 7 the equation would be 2&#8310;(2&#8311; - 1) resulting in the perfect number, [8128](https://en.wikipedia.org/wiki/8128_(number)) which is a [triangular number](https://en.wikipedia.org/wiki/Triangular_number). It's also the result of [64](https://en.wikipedia.org/wiki/64_(number)) * [127](https://en.wikipedia.org/wiki/127_(number)). The number 64 has seven factors and is a [centered triangular number](https://en.wikipedia.org/wiki/Centered_triangular_number) while the number 127 is a [Mersenne prime](https://en.wikipedia.org/wiki/Mersenne_prime) and a [centered hexagonal number](https://en.wikipedia.org/wiki/Centered_hexagonal_number).

Another way of thinking about the seven-letter *almsivi* as a numeric motif is that in a system where the number One is akin to God, Two is evenness, and Three is pivotal balance, Seven is a number that signifies cyclical completeness (7 days in a week, 7&sup2; weeks in a year, 7 years in a [Chakra cycle](https://en.wikipedia.org/wiki/Chakra#The_seven_chakra_system), or 7 Sabbatical cycles in a [Jubilee](https://en.wikipedia.org/wiki/Jubilee), etc.).

Numbers play a significant aspect in Dunmer culture and they are present all throughout [sacred](https://en.uesp.net/wiki/Morrowind:The_36_Lessons_of_Vivec) texts, forming the basis of their [very understanding](https://en.uesp.net/wiki/Morrowind:Sithis) of the cosmos.

###### In Daedric script, holy words are sometimes written in red. Specify the color in the span tag like so:
```html
<span style="font-family:HayghinDaedric; color:red">ASV</Span>
```

Based on [some](https://www.etsy.com/listing/223690247/the-tribunal-gods-of-morrowind-print) of the [examples](https://en.uesp.net/wiki/Category:Morrowind-Banner_Images) that I have seen, it would appear that red is an honorific color that may represent holy names, powerful words, or strong emphasis, when writing in the Daedric script. As a matter of propriety, I try to highlight sparingly and only where it seems contextually appropriate to do so.

---

## Further Reading

It seems relevant to have a look at [Earthsea](https://en.wikipedia.org/wiki/A_Wizard_of_Earthsea) and it's use of [*Rumpelstiltskin theory*](https://sjaakvandergeest.socsci.uva.nl/pdf/anthropology_and_literature/rumpelskin.pdf) or the idea that [*True* words](https://en.wikipedia.org/wiki/True_name) may have power. There [seems to be](https://www.reddit.com/r/teslore/comments/1ptr0o/i_am_michael_kirkbride_ask_me_anything/cd5y2n5?utm_source=share&utm_medium=web2x&context=3) a [similar current](https://www.imperial-library.info/content/posts-kirkbride-undated#node-8393:~:text=On%20Vivec%20and%20Morrowind) present in many Tamrielic religions and languages. Alongside Hinduism and Christianity, Morrowind also saw influence from [Thelema](https://en.wikipedia.org/wiki/Thelema) and it's [Book of the Law](https://en.wikipedia.org/wiki/The_Book_of_the_Law).

The Tribunal Faith and it's influence on Dunmer culture cannot be understated. The Temple has what can be considered an "[open canon](https://en.wikipedia.org/wiki/Biblical_canon#:~:text=In%20contrast%2C%20an%20%22open%20canon,their%20respective%20faiths%20and%20denominations.)" of scriptures which have evolved over time and region to encompass many texts. Some of the most seminal works include:

- [The Homilies of Blessed Almalexia](https://en.uesp.net/wiki/Lore:Homilies_of_Blessed_Almalexia) (<span style="font-family:HayghinDaedric">as malyudhardii</span>, As Malyudhardii, lit., "the homilies")
- [The Truth in Sequence](https://en.uesp.net/wiki/Lore:The_Truth_in_Sequence) (<span style="font-family:HayghinDaedric">as leyrihn</span>, As Leyrihn, lit., "the sequence")
- [The 36 Lessons of Vivec](https://en.uesp.net/wiki/Lore:The_36_Lessons_of_Vivec) (<span style="font-family:HayghinDaedric">as shoreshiik</span>, *As Shoreshiik*, lit., "the lessons" )

Collected and canonized texts are often reflective of the local temples and their communities, however.

To learn more about Dunmer culture, have a look at the following resources:

- [A Pocket Guide to the Empire: Morrowind](https://www.imperial-library.info/content/pocket-guide-empire-first-edition-morrowind), an outdated leaflet reflecting some historic racial views towards the Dunmer
- [Fellowship of the Temple](https://en.uesp.net/wiki/Lore:Fellowship_of_the_Temple) (<span style="font-family:HayghinDaedric">daeljuha am as daenthi</span>, *Daeljuha am As Daenthi*), an introductory pamphlet on The Tribunal Temple
- [Organization of the Temple](https://www.reddit.com/r/teslore/comments/1on7gw/a_short_introduction_to_the_tribunal_temple/)
- [What is the Religious History of the Dunmer?](https://writteninuncertainty.com/podcast/dunmer-religion/)
- [Dunmer Beliefs and Customs of the Dead](https://en.uesp.net/wiki/Lore:Death#Dunmer_Beliefs_and_Customs)
  - [The Doors of the Spirit](https://en.uesp.net/wiki/Lore:The_Doors_of_the_Spirit)
  - [Blasphemous Revenants](https://en.uesp.net/wiki/Lore:Blasphemous_Revenants)
- [The Metaphysics of Morrowind](https://fallingawkwardly.wordpress.com/2010/08/29/the-metaphysics-of-morrowind-part-1/)
- [The Oghma Infinium](https://en.uesp.net/wiki/Lore:Oghma_Infinium), which depicts the Aurbis and the Enantiomorph
- [The New Whirling School Commentary](https://www.newwhirlingschool.com), A major work-in-progress commentary on the 36 Lessons
  - [Intro to Terminology](https://www.newwhirlingschool.com/intro.php)
  - [Exploratory Essays](https://www.newwhirlingschool.com/intro.php#essays)
- [Jerome's Short Commentary](https://jeromeiv-blog.tumblr.com/post/19934786003/sermon-1-of-36-lessons-of-vivec-dissection), incomplete but venerably covers the first six chapters of the 36 Lessons
- [La symbolique de l'alphabet daedrique](https://arador-dayn.fr/viewtopic.php?f=16&t=449), *The symbolism of the Daedric alphabet*

Finally, some further essays and topics relating to Morrowind:

- [Religion in Computer Games](http://kau.diva-portal.org/smash/get/diva2:508317/FULLTEXT01.pdf), an essay by Jon Ode that explores the forms and implications of religion in games using Morrowind as the example
- [A Treatise on the Subject of Daedra Worship](https://luke-a-fytch.itch.io/a-treatise-on-the-subject-of-daedra-worship), an essay by Luke A. Fytch that details the emergence of a new form of pop-culture paganism
- [Prophecy, Pre-Destination, and Free-form Gameplay](https://heiup.uni-heidelberg.de/journals/index.php/religions/article/view/18512/12320), an essay by Angus Slater from the Heidelberg Journal of Religions on the Internet, Vol. 7, pg. 161 that explores the Nerevarine Prophecy's affect on gameplay
- [A Game About Textual Interpretation](https://goingpewpew.com/2017/04/23/blog-post-title-3/), a blog post by Eric Farr that examines the role that text and language plays in the Elder Scrolls

---

## Publishing Your Work

It's easy to convert Markdown to PDF. With your viewer of choice, you can use your operating system's *Print to PDF* feature.

It's also very easy to convert formats using [pandoc](https://pandoc.org/):

```
pandoc example.md --standalone --output example.pdf
```

Finally, GitHub has a [guide to publishing pages](https://guides.github.com/features/pages/) if you too would like to take your markdown and turn it into a website like this one.

---

## Final Words

I'm no language expert and there's plenty I have not accounted for. The irreverent, more clinical emphasis of Telvanni subculture has had an affect on the language. [Architecture plays a key role](https://ajmchugh.wordpress.com/2019/06/19/how-vivec-city-reinforces-morrowinds-politics/) in Dunmer expression as well and it varies wildly between regions. There is also the influence of [House Dres](https://en.uesp.net/wiki/Lore:House_Dres) and the practice of slavery throughout Morrowind, as well as it's [eventual ban](https://www.imperial-library.info/content/pocket-guide-empire-third-edition-temple-morrowind#node-1966:~:text=outlawed%20slavery%20throughout%20Morrowind).

|The Twin-lamps light the way to freedom|
|:-:|
|As asc'aaf sincag as manidi de julgham|
|<span style="font-family:HayghinDaedric">as asc'aaf sincag as manidi de julgham</span>|

The series can [trace it's roots](https://rpg.stackexchange.com/questions/89399/is-morrowind-based-on-a-tabletop-rpg/89416) to [RuneQuest](https://en.wikipedia.org/wiki/RuneQuest), set in the world of [Glorantha](https://en.wikipedia.org/wiki/Glorantha). There is something to be said of the similarities between the Dunmer and the [pre-Roman Celts](https://en.wikipedia.org/wiki/Insular_Celts) as well.

My point is that there is a lot to be observed and discovered about Morrowind and I am barely scratching the surface as I write down what little I've learned. I don't intend for this to act as any primary source, just a quick point of reference.

Now go have fun, get into the spirit of things, and don't take anything too seriously!

---

