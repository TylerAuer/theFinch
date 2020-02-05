# The Finch

A publishing platform for [Saint Andrew's](https://www.st-andrews.org/) students built with [Jekyll](https://jekyllrb.com/) & [Bootstrap](https://getbootstrap.com/).

- [The Finch](#the-finch)
  - [Reflections](#reflections)
    - [What Works Well](#what-works-well)
    - [What Could be Better](#what-could-be-better)
    - [Why Jekyll?](#why-jekyll)
  - [Common Actions for Maintaining The Finch](#common-actions-for-maintaining-the-finch)
    - [New Post](#new-post)
    - [Add Contributor or Category](#add-contributor-or-category)
  - [Special CSS Classes and Includes Used in Posts:](#special-css-classes-and-includes-used-in-posts)

## Reflections

After I complete a project, I make it a habit of reflecting, in writing, with what I learned and what I would do differently. A few ideas:

### What Works Well

- **Easier Maintenance**: Maintaining this version of The Finch is much easier than the initial Wordpress version. This is mostly because the online Wordpress editor is slow and because adding an author meant creating a new student account.
- **Speed**: This site loads more quickly and performs better because it serves static HTML, CSS, and JavaScript files. This difference is exacerbated by the fact that the school has a minimal hosting plan which likely makes the PHP processing for Wordpress much slower.
- **I Am Smarter Than I Was**: I know more than I did when I built the Wordpress site, so this site is constructed much better. The CSS is simpler (thanks to the use of SASS) and there is less repetition of code.

### What Could be Better

- **Automatic Generation of Categories and Contributors Pages**: Maintenance of the site would be easier if I had used a plugin to automatically generate the simple contributor and categories pages. Then all contributors and categories could live in a simple YAML document like the navigation does.
- **Student Development Page**: Theres a lot of additional features I'd like to add to make it easier for students to develop posts.
- **Slugify Filter for Links**: The most challenging aspect of this project was fixing a bug that was breaking links to category and contributor pages. Much of this could have been avoided had I know about the [Liquid slugify filter](https://jekyllrb.com/docs/liquid/filters/).

### Why Jekyll?

This project is a rebuild of a version of The Finch which previously had a Wordpress backend. After a year, we found that Wordpress was failing us in two ways:

1. The site was slow, even with caching. This may have been solved by upgrading our hosting plan, but that was an undesirable option for the school.
2. Students without any HTML or CSS knowledge struggled to help turn student writing into publish-ready documents. Since we want students to own as much of the site as possible, I looked for a solution that would be easier for the students.

This new version of the site serves the students' needs much better and we look forward to using it for a number of years.

## Common Actions for Maintaining The Finch

Processes that should be followed when doing routine work on the site.

### New Post

When a new post is ready for publication, follow these steps:

1. In `/_posts` folder make a copy of `template.md`
2. Rename file using Jekyll naming convention: `YYYY-MM-D-TITLE-WORDS-SEPARATED-BY-DASHES.md`
3. Add header image to `/assets/**images`
4. Update liquid template with appropriate information
5. Add new [contributors](#add-contributor) or new [categories](#new-category) as needed
6. Run `jekyll build`
7. Send updated files in `/_site` to hosting service

### Add Contributor or Category

A **contributor** is anyone who helps work on a post. All student contributors use pseudonyms to protect their identity. Contributors fall into one or more of the following categories:

- Authors
- Artists
- Copy Editors
- Technical Editors

Categories describe the genre(s) of the writing each posts falls within.

**Follow the following steps to add a contributor or category:**

1. Make a copy of the template file:
   - **Contributor**: `/_contributors/template.md`
   - **Category**: `/_category/template.md`
2. Rename the copied template using the naming convention:
   - **Contributor**: `FirstLast.md`
   - **Category**: `name-of-category.md`
3. Update the liquid template heading

## Special CSS Classes and Includes Used in Posts:

- `.dropcap` - Used to create a dropcap at the start of the paragraph. To use, wrap first letter of a paragraph in a `span` tag. Ex:
  ```HTML
  <span class="dropcap">It</span> is recommended that you
  you enclose both characters of a two-letter word, in the
  dropcap span
  ```
- `.indent` - Used to indent text, often as part of a poem. Can also be used for a tab-style space in the middle of the line. Use a self-closing `<span/>` tag where you'd like the space
  ```HTML
  <span class="indent"/>This paragraph would be indented. And,
  there would be an indent <span class="indent"/> <--here.
  ```
- Include a section break by using the Jekyll include command:
  `{% include section-break.html %}`
