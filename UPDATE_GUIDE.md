# A guide for updating the website

Hello dear reader! What follows is a how-to guide of how to update relevant portions of the website.

## Table of contents
1. [Getting Started](#getting-started)
2. [Adding pdfs and links](#adding-pdflinks)
3. [Adding images](#adding-images)

Updating various sections

4. [News](#news)
5. [Projects](#projects)
6. [Publications](#publications)
7. [People](#people)
8. [Funding](#funding)

General

9. [Visual Edits](#visual-edits)
10. [Saving work](#publishing-your-changes)

## Getting Started
Editing the website will require two things.

1. A github account
2. Access to the Repository

In order to access the repository, you will need to be explicitly added to it. It is currently managed by Michelle Johnson, who can be reached at [mljohnson@g.hmc.edu](mailto:mljohnson@g.hmc.edu)

Once you have access, you can edit the website and files in two ways. First, through the website on [the Github](https://github.com/HayLab/haylab.github.io). Once you're logged in, you can click on a file and should have the option to edit each one and even add new files. Or, by cloning the repository and using your favorite developing shell (we recommend [VSCode](https://code.visualstudio.com/), which has excellent [tools for working with github](https://code.visualstudio.com/docs/sourcecontrol/github))

## Adding pdf/links

If you want to add clickable link to a page, the format is as follows:

```<a href="link_to_object">words to click on</a>```

If you want to make reading a pdf easy, add the pdf file to the "assets/pdf" folder, and link to it as such:

```Read the pdf <a href="/assets/pdf/Hay2025_proof.pdf">here!</a>```

You can also link to outside websites if desired, simply by changing the href to the website you want. For example:
```Learn more at <a href="https://en.wikipedia.org/wiki/Gene_drive">Gene Drive Wikipedia</a>```

## Adding images

You should be able to add an image using the following syntax:

```
<div class="figure">
    <img src="{{ site.baseurl }}/assets/img/cell death and mitochondrial quality control.jpg" title=""  class="img-fluid"/>
</div>
```

The image source should link to the title of the image you've added to the "assets/img" folder. To change the size of the image, you should be able to add a "width" parameter as follows:

```
<div class="figure">
    <img src="{{ site.baseurl }}/assets/img/cell death and mitochondrial quality control.jpg" title=""  class="img-fluid" style="width: 20%"/>
</div>
```

You can set the width to be a certain percentage of its onscreen space, using "X%" (10%, 200%). You can also set an image to be a fixed size, using "Xpx" (7px, 300px), or to be relative to the font size, using "Xem" (1em, 40em). Learn more about sizing [here](https://www.w3schools.com/cssref/css_units.php).

## News

To add a news line to the front page of the website, you must add a new file in the folder `_news`. The file must follow the naming convention of `[year]_[month]_[day]-[label].md`. The label you provide here doesn't make its way to the website, but makes keeping track of your posts easier.

The file must start with a header, as follows:

```
---
layout: post
date: 2025-06-06
inline: true
related_posts: false
---
```

Here, you specify that you want to make a post, you specify a date for the post, and you can decide whether it will be an "inline" post, or not. An inline post will just show up in a single line on the about page. However, if you want to make a longer post (taking up multiple lines or paragraphs), you can instead set the inline value to false:

```
---
layout: post
date: 2025-06-06
inline: false
title: Short Title To Be Clicked On
related_posts: false
---
```

Here, you'll provide a *title* that will appear on the main about page. When clicked on, it will redirect to a page with the rest of your text. 

Once you've added this header to the page, start typing away! The github repository will configure the rest

The home page of the website only shows the 5 most recent news posts. To change this number, go to the file `_config.yml` and change the variable `news_limit`.

## Projects

To add a project, add a file in the "_projects" folder. The file must include the following header:

```
---
layout: page
title: Controlling the composition and fate of wild populations
description:
img: /assets/img/population modification.jpg
importance: 2
---
```

We use this to specify that the project links to a *page*. It must have a *title* which will be displayed on the projects page. A short *description* can also be added. The *img* denotes what image will appear on the projects page, and should link to an image added to the assets/img folder. We must also give the project an *importance*. This signifies where on the page the project should go. A project of importance "1" will appear first, "2" will appear second, etc. We recommend that each project should get its own number.

## Publications

To add a publication, begin by uploading a pdf with a helpful and easily distinguishable name to `assets/pdf`. 

Then, edit the file `_bibliograph/papers.bib`, and add a new entry to the top.

Here's a breakdown of one example:
```
@article{Johnson2024,
  title={Altering traits and fates of wild populations with Mendelian DNA sequence modifying Allele Sails},
  author={Johnson, Michelle L. and Hay, Bruce A. and Maselko, Maciej},
  journal={Nature Communications},
  year={2024},
  pdf={Johnson2024.pdf},
  supp={Johnson2024Supplemental.pdf}
}
```

The article must be added using the `@article{ }` tag. Inside the brackets, we start by putting a short label, that identifies the paper we're going to add. We then add different parameters one at a time. We give the Title, a list of the Authors, the name of the journal, and the year it was published. Finally, put add the name of the pdf you want to link to in the pdf parameter.

Optionally, you can also add other links. There are many link button options, as follows

- abstract
- arxiv
- bibtex_show
- html
- pdf
- preprint
- supp
- blog
- code
- poster
- slides
- website
- pr1 (stands for "press release")
- pr2 (allows for second press release)
- abstract

To see the details of the buttons, or to add your own, check out `_layouts/bib.html`.

**NOTE:** The list of *years* that are displayed can be found in `_pages/publications.md`. When adding a paper from a new year (such as 2026), you MUST go into publications.md, and add the year to the beginning of the list. Otherwise, the paper will be hidden.

## People

To add or edit people, go to the page `_pages/people.md`. Each person's entry has the following syntax:

```
<div class="col">
    {% include figure.html path="assets/img/Georg.jpg" class="img-fluid rounded z-depth-1" %}
    <strong>
      <center>
        Georg Oberhofer
      </center>
    </strong><br>
    Postdoctoral Fellow, PhD
  </div>
```

This includes a path to their image, their name, and their title. We recommend, for consistency, that all images of people in the same row should be the same crop ratio.

To break people into rows, we have inserted the line `<div class="w-100"><br></div><br>`. This creates a break in the people, allowing for a new row. When adding or removing people, make sure that you move these break lines accordingly

## Funding

The html of this page can be edited directly in the file `_pages/funding.md`

## Visual Edits

So, you think the website looks ugly. It could use a fresh coat of paint, or maybe text boxes that fit together snugly. Let's talk about some website basics!

**HTML**. Most of this website is coded directly in HTML. This includes the markdown files in `_pages`, along with the html files in `_includes` and `_layouts`. For basic formatting, I recommend looking through the html first.

*Tip:* If you have an idea for some html editing, you can try it out in the broswer first. Go to the webpage you want to change, right click the page, and select "Inspect". You can now view the html itself, and make edits. I like using this trick to make sure the style tags I'm adding will actually do what I want them to. Once you're happy, you can come back to the code and add your final edits here.

**CSS**. Html covers the basics - the *very* basics - of how text and images are arranged onscreen. For things like colors, box highlights, and margins, you'll have to look for the CSS. Colors appear to be handled by `_assets/css/jekyll-pygments-themes-github.css`. Other css files can be found in the `_sass` folder.

**JS**. Javascript usually handles things like buttons, and clicking, and actions on the website. Find all the javascript files in `assets/js`

I'm fairly certain the `_config.yml` also has a visual effect on the website.

## Publishing Your Changes

For a change to make it from the base code to the website that anyone can see, the change first must be saved to the repository. 

**On the website**, after editing a file click the "Commit Changes" button, in green on the top right. You'll be prompted to add a "Commit message." *Please* use this space to add a descriptive message of the change you just made. Make sure you "Commit directly to the `source` branch", and click "Commit changes" in the bottom right.

**In VSCode**, a change must be both committed *and* pushed to the source repo in order for it to be recorded.

After a change is saved, the github repository automatically creates an **Action** called "pages build and deployment". This does the work of adding your change to the website. You can view the status in the "Action" tab of the github website. A yellow circle next to the most recent action means it is still making changes. A green check means the change has been deployed, and you should be able to view it at [haylab.caltech.edu](https://haylab.caltech.edu/). A red X means something has gone wrong, and you should contact your administrator.

Congrats! You have just made your first changes to the website.