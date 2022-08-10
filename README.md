# THE FANDOM CODERS ENCYCLOPÆDIA

This is the official repository for _The Fandom Coders Encyclopædia_,
  an encyclopedia of technological concepts built by the
  [Fandom Coders][] community.
The encyclopedia is built using Jekyll and hosted via GitHub Pages.

## How To Contribute

Contributions can be submitted via pull requests on GitHub.

You can follow [this guide][GitHub-Pages-Locally] to set up a local
  environment for developing and testing the encyclopedia.

### Organizational Structure

All site pages are placed in `_pages/❲_type❳/❲S❳/❲slug❳.html`,
  where :—

+ `❲_type❳` is the type of page, prefixed with an underscore. The
  following types are available :—

    + `entry` pages provide encyclopedic entries on a particular topic.

    + `help` pages provide assistance regarding use of the site.

    + `meta` pages provide guides and other supplementary information.

    + `topic` pages provide taggable topic indices.

    + `word` pages provide dictionary definitions for various words.

+ `❲S❳` is either :—

    + The first letter of the page slug, capitalized, if the page slug
      starts with a letter.

    + `&`, if the page slug starts with anything else.

+ `❲slug❳` is the full page slug. Page slugs can’t contain spaces.

### Sample Entry

A minimal entry might look as follows :—

```html
---
title: sample entry
subtitle: kind of example page
dym:
- sample_in_tree
related:
- other_entry
topics:
- sample_pages
---
<p>
	A <dfn>sample entry</dfn> is an entry which is used as an example.
	Most entries should begin with a single top‐level paragraph like this explaining what the thing is that they describe.
</p>

<section id="subsection">
	{% include heading level=3 section="subsection" text="Sample Subsection" %}

	<p>
		Additional information is often contained in subsections like this one.
	</p>
</section>
```

### Titles and Slugs

Pages are identified in a number of ways :—

+ The *full title* of a page gives the fully‐qualified, human‐readable
    name for a concept.
  It is defined as the `title` property of the YAML frontmatter of a
    page.

+ The *short title* of a page gives a shorter form of the title which
    is more suitable for links in running text.
  It is not required that pages have a short title, but when they do,
    it is defined using the `shorttitle` property of the YAML
    frontmatter of a page.
  Short titles should still be unique.

+ The *subtitle* of a page describes the general category of thing that
    the page’s subject belongs to.
  It is defined using the `subtitle` property of the YAML frontmatter
    of a page.
  All entries should have subtitles, which should be written such that
    the following sentence makes grammatical sense :—

  > ❲Title❳ is/are a ❲subtitle❳.

  Subtitles are not necessary for other kinds of pages (words, meta,
    etcetera).

+ The *slug* of a page gives its title as it appears in URL’s and is
    used to generate crosslinks.
  Slugs are derived from the filenames of pages and should not contain
    spaces or characters which are not allowed in URL’s.

### Crosslinks

Words, entries, and topics which share a slug will be crosslinked
  automatically.

Additional topics can be listed under `topics` in the YAML frontmatter
  for entries, and related entries can be listed under `related`.
`dym` (short for “did you mean…?”) can be used to list related entries
  which the user might have intended instead.

### Page Markup

All source pages are written in HTML and make use of Jekyll tags for
  additional functionality.
The following tags might be helpful :—

+ `{% include link to="slug" %}` includes an internal link to another
    page.

    `from` can be used to specify the collection; it defaults to
      `site.words` for words and `site.entries` for all other kinds of
      pages.

    `full`, if true, indicates the full title of the page should be
      used (for example, “Meta::Introduction to the Encyclopædia”
      instead of “※Introduction”).

    `text` can be used to override the link text.

+ `{% include link href="http://example.com" %}` includes an external
    link to another page.

    `banner` can be used to specify a banner image for external links.

    `text` can be used to provide the link text.

+ `{% include heading level=3 section="identifier" text="title" %}`
    creates a section heading. The `level` attribute gives the level
    of the heading (typically starting at 3); the `section` attribute
    should give the `id` of the `<section>` element which wraps the
    heading, and the `text` attribute gives the heading text.

+ `{% include cf items="slug1 slug2 slug3" %}` creates a “See Also”
    heading pointing to the pages with the provided slugs.

### Missing Entries

If you know that an entry is missing, you can keep track of it by
  adding it to `_data/todo.yml`.
It will then appear in `/TODO/` as an easy reference point for future
  work.

 - - -

The Fandom Coders Encyclopædia

The content of this encyclopedia (in the `_pages` directory) is
  licenced under the
  [Creative Commons Attribution-ShareAlike 4.0 International License][CC BY-SA].
The underlying technical code, not including the `_pages` directory, is
  licensed under the [MIT License][].
By contributing to this repository, you agree to licence your content
  under these terms.

[CC BY-SA] <https://creativecommons.org/licenses/by-sa/4.0/>
[Fandom-Coders] <https://github.com/Fandom-Coders>
[GitHub-Pages-Locally] <https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll>
[MIT License] <https://choosealicense.com/licenses/mit/>
