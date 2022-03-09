
---

<!--- Local CSS Font Loading -->

<style>
@font-face {
    font-family: HayghinDaedric;
    src: url('../../../assets/fonts/ttf/HayghinDaedric.ttf') format('truetype');
    font-weight: medium;
    font-style: normal;
}
</style>

<!--- Jekyll Page Links -->

<center>
<a href="../../../index.html">Home</a>
&emsp;&nabla;&emsp;
<a href="../../archive/about.html">About</a>
&emsp;&nabla;&emsp;
<a href="../../archive/index.html">Archive</a>
&emsp;&nabla;&emsp;
<a href="../index.html">Quintessence</a>
</center>

<!--- Markdown Body Below: -->

---

## QUINTESSENCE


#### How to Print

Printing something on Lulu is really easy but first you will need to download the interior and cover pdfs.

Next, create an account at [lulu.com][1] and head to your [Projects Page][2] to create a new project.

On the Start page, be sure to set a category (it's a required field, I guess?). For fun, I chose "Religion & Spirituality" but there are other applicable categories as well, such as "Games" and "Fiction".

Below are the steps I used on the Design page to set up my book:

__Product Type:__ Print Book\
__Goal Option:__ Print Your Book\
__Interior File:__ [*us_trade_interior-codex_sinramus.pdf*][3]\
__Book Specifications:__\
&emsp;__Size:__ US Trade\
&emsp;__Interior Color:__ Color Standard\
&emsp;__Paper Type:__ #60 White\
&emsp;__Book Binding:__ Hardcover\
&emsp;__Cover Finish:__ Glossy *or* Matte\
__Cover File:__ [*us_trade_hardcover-codex_sinramus.pdf*][4]

There will be two minor warnings to look out for:

When you upload the interior file, you will receive a warning that some images within might have lines that are too thin for the printer to handle. This won't prevent you from proceeding. The line thickness error has to do with the fine detail in the fresco images. Some small rings that show up in digital are too small for the printhead. I received this warning every time, but it is a total false positive.

At the end, the preview window doesn't seem to account for spine and gutter adjustment. If your preview [looks like this][5], you are seeing the same probable error that I saw. The book still printed correctly, however.

If you are worried about the measurements, please feel free to have a look at the Lulu design documentation below, under __Making Modifications__.

__A note on the cover finish:__ I chose matte because I was going for an old bound leather(ish?) appearance. Obviously, that's not so easy to accomplish with a mass-produced cardboard cover, so I settled on a flat color for the cover in order to pull off some semblance of my odd vision without trying to kid myself too much.

I didn't know what to expect of the result, but it turns out that the mix of the paper surface and ink color lead to a bit of smudginess. I decided to just rip that band-aid and smudge up the whole cover with my palm for a nice weathered look, but it's hard to tell on my potato cam, and some people might not like it.

The best option is to just print glossy. However, you can also make your own cover with the template files, or you could try the more limited but fairly easy online tool that the website provides. There's also a book-jacket option, but I haven't looked into it. Either way, I figured people would want to know ahead of time. It's theoretically possible that the matte cover could wrinkle as well, if not protected.

__I think most people will want a glossy coating for it's sturdiness.__

[1]: https://www.lulu.com/
[2]: https://www.lulu.com/account/projects
[3]: https://github.com/mmillar-bolis/MDunmeris/releases/download/1.3/us_trade_interior-codex_sinramus.pdf
[4]: https://github.com/mmillar-bolis/MDunmeris/releases/download/1.3/us_trade_hardcover-codex_sinramus.pdf
[5]: https://github.com/mmillar-bolis/MDunmeris/blob/gh-pages/documents/quintessence/previews/lulu_funky_preview_pane.png?raw=true

---

#### Making Modifications

The first thing you will want to grab is a copy of the book design reference guide.

[__Lulu Book Creation Guide__][6]

If you would like to make your own modifications to the Quintessence, my OpenDocument project file, as well as all of the image and font assets can be found in the [project folder on GitHub][7], or at the link for the [Quintessence Release Page][8] section above. Here's a direct link to the resource bundle in a `.zip`:

[__Source Document and Resource Bundle__][9]

When exporting to PDF, I use the archive format PDF/A-1b to ensure there is no transparency in raster images.

The cover is measured for a 17mm spine. I actually did a print at 16mm and the title was cramped. Yes, the design guide says that up to 168 pages the spine should be 16mm, but here's the interesting part: with Lulu, the first page is not in the first signature, but on a sheet fixed to the end paper. 14 signatures at 6 sheets each is 168 pages, but the two end sheets actually round the book up to 170. I don't know; I tried to account for the measurements on everyone's behalf, but let's face it, print-on-demand can be a little chaotic with self-made covers by amatures. A few prints so far with no issues but fingers crossed!

[6]: https://assets.lulu.com/media/guides/en/lulu-book-creation-guide.pdf
[7]: https://github.com/mmillar-bolis/MDunmeris/tree/gh-pages/documents/quintessence/project
[8]: https://github.com/mmillar-bolis/MDunmeris/releases/
[9]: https://github.com/mmillar-bolis/MDunmeris/releases/download/1.3/quintessence-project-source-bundle.zip

---
