# Hosting a resume on GitHub pages using Jekyll.

This text provides and describes the practical steps of how to host and format a [resume](https://eliesercapillar.github.io/resume/) using **Markdown, Atom, GitHub Pages, and Jekyll**.

Additionally, this text will show the value of pursuing this approach with the help of _Andrew Etter's_ book, [Modern Technical Writing: An Introduction to Software Documentation](#MoreResources).

## Table of Contents
- [Prerequisites](#Prerequisites)
  - [A Resume in Markdown](#Resume)
  - [A Markdown Editor](#Editor)
  - [A GitHub Account](#GitHub)
  - [Git](#Git)
  - [Jekyll](#Jekyll)
  - [GitHub Desktop](#GHDesktop)
- [Instructions](#Instructions)
  - [Creating a static website using Jekyll](#CreatingWebsite)
  - [Adding your resume to your site](#AddingResume)
  - [Hosting your site on GitHub Pages using GitHub Desktop](#HostingSite)
- [FAQs](#FAQs)
  - [Why is Markdown better than a word processor?](#Q1)
  - [Why is my resume not showing up?](#Q2)
- [Author and Acknowledgements](#Authors)
- [More Resources](#MoreResources)

## Prerequisites <a name = "Prerequisites"></a>

Before starting, you will need these prerequisites:

### A Resume in Markdown <a name = "Resume"></a>
![Elieser's Resume](/assets/gifs/eli_resume_slide.gif)

In order to host a resume like [what I have on this site](https://eliesercapillar.github.io/resume/), you will first need a resume written in Markdown.

If you need a refresher on Markdown, I have listed an excellent resource which can be found in [More Resources](#MoreResources).

### A Markdown Editor <a name = "Editor"></a>
In order to write in Markdown, you will need a Markdown editor.

I use [Atom by GitHub](https://atom.io/).

Any text editor will work, but I appreciated Atom's customizability as well as its built in integration with GitHub.

### A GitHub Account <a name = "GitHub"></a>
In order to host a resume on [GitHub Pages](https://pages.github.com/), you will need to have a GitHub account.

If you do not yet have one, you can make one on the [GitHub Website](https://github.com/).

### Git <a name = "Git"></a>
In order to make use of GitHub and the ability to push files into a repository, you will need Git.

If you do not yet have Git installed, you can follow [this guide](https://github.com/git-guides/install-git) from GitHub.

### Jekyll <a name = "Jekyll"></a>
Lastly, you will of course need [Jekyll](https://jekyllrb.com/).

If you do not yet have Jekyll installed, you can follow this tutorial on the [Jekyll Website](https://jekyllrb.com/docs/installation/).

### GitHub Desktop <a name = "GHDesktop"></a>
This is optional. [GitHub Desktop](https://desktop.github.com/) is a GUI for git.

With this tool, pushing local reposities onto your online repository can be done with a only a few clicks.

## Instructions <a name = "Instructions"></a>
Once you have all of the prerequisites, you are ready to host your own resume on GitHub Pages.

From _Andrew Etter's_ book, which can be found in [More Resources](#MoreResources),  

> I mentioned earlier that you should build and host a website, not distribute PDFs, but it bears repeating. Even the best documentation, like software, eventually goes out of date. PDFs get downloaded onto hard drives and then sit there like day-old bagels, growing more and more stale until they're actively harmful. **You can never update them.**

Andrew clearly states the value of having documentation contained on the web. It is much easier to maintain and update, but most importantly, **push those updates immediately to users**.

Instead of having to provide potential employers with a copy of our resume, we can simply give a link to the website where our resume is hosted. This ensures employers are always given the most up-to-date version of our resume.

### Creating a static website using Jekyll <a name = "CreatingWebsite"></a>  

So how do we create a static website using Jekyll? We will be using a terminal to accomplish this.
1. Open your terminal of choice.
2. Change to the directory you want your website files to be saved in.
3. Create a new site by typing the following into your terminal:  
`jekyll new your_sites_name`


Jekyll has now made your new site. In order to view it, the site has to be built. There are two ways to do this:
1. `bundle exec jekyll build`
    - This will perform a one off build to the directory `./_site`. This contents in `./_site` can then be given to your web-host and they will serve the site for you.
    - This option is used to deploy to production.
2. `bundle exec jekyll serve`
    - This will build your site anytime a source file changes, and serves it locally.
    - This option is used for development.

For now, we will only be using `bundle exec jekyll serve` to host our site locally, until we are ready to deploy.

I recommend reading up on the [Jekyll documentation](https://jekyllrb.com/docs/) to learn more about these commands and other commands I did not cover.

### Adding your resume to your site <a name = "AddingResume"></a>

You may be wondering: is it really worth going through all of this effort just to host my resume online?

_Andrew Etter_ says,

> ... links are one of the most wonderful things the Internet has given us. The
most popular sites on the Internet are devoted, in fact, to the sharing of links
between friends and strangers. Making proper use of links lets us attain a
sort of Holy Grail in technical writing: **single sourcing**

The value behind hosting our documentations online is that it is altogether in a place that is easy to find and edit.

With the average Software Engineer churning through hundreds of potential employers throughout their career, having to alter each and every resume to cater to the job is a mind-numbing task can add up to weeks of lost time, maybe even more.

So how do we add our resume onto our newly built site?
1. Add your `resume.md` file in the directory that contains your website.
2. Modify the file to add [_Front Matter_](https://jekyllrb.com/docs/front-matter/) at the top of the file.
    1. Add a title.
    2. Specify the layout type.
        - Any files of layout type: `post` must be in the `_posts` directory with the following naming convention: **YYYY-MM-DD-fileName.md**
    3. Create a permalink for the file
        - This is an important step. If a permalink is not set, future changes may **break** the link to this file and prevent employers from accessing your resume.

### Hosting your site on GitHub Pages using GitHub Desktop<a name = "HostingSite"></a>   

If you do not have [GitHub Desktop](https://desktop.github.com/), a terminal will work fine.

1. Create a new repository by going to `File` &rarr; `New Repository`.
2. Name the repository to _username_.github.io, where _username_ is your username on GitHub.
3. Add your website project folder onto the new repository using your tool of choice.
    - I personally use a Git GUI like [GitHub Desktop](https://desktop.github.com/).
4. Commit the changes.
5. Push the changes to your repository.

## Frequently Asked Questions <a name = "FAQs"></a>
### "Why is Markdown better than a word processor?" <a name = "Q1"></a>
Markdown is not necessarily _better_ than a word processor. Both are tools built for certain tasks, and both tools do these tasks well.

Markdown excels in its incredible flexibility, allowing Markdown files to be ported to many- often distinct systems- with ease.

Comparing this to a word processor like Microsoft Word and its DOCX file format, _Andrew Etter_ says,

> Documentation with any sort of
lifespan needs to be kept in version control, which Word's DOCX file
format (a compressed collection of XML files) actively opposes.

When it comes to documentation that requires fast and constant iteration, Markdown shines.

### "Why is my resume not showing up?" <a name = "Q2"></a>

Depending on your Jekyll theme and its `_layout` files, your content may or may not appear right away when you add your `resume.md` file.

Some Jekyll themes implement layouts for `pages` while others do not and only implement `posts`.

Others may implement `pages` and `posts` but depending on the implementation of `index.md` or  `default.html`, these `pages` and `posts` still may not appear.

Upon picking a theme, carefully read its GitHub repository. Pay special attention to the `_layouts` folder. There may not exist an implementation for the Front Matter layout you put in your file.

## Author and Acknowledgements <a name = "Authors"></a>
Written by _Elieser Capillar_ (#7838502)


Edited by the members of Group 13:
- Peter Krompiewski
- Jeonghwan Choi
- Devam Patel

Jekyll Theme by [_Oinam_](https://github.com/oinam/oinam-jekyll)

## More Resources <a name = "MoreResources"></a>

Here is a list of resources I found useful while working on this project:
- A very easy to read, [Markdown syntax overview](https://www.markdownguide.org/basic-syntax).
- A cheat sheet to [GitHub-flavoured Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
- A great [Jekyll Tutorial on Youtube](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB) by _Mike Dane_.
- [Modern Technical Writing: An Introduction to Software Documentation](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS) by _Andrew Etter_
