### Notes to self

Config currently coded to the [Modernist](https://github.com/pages-themes/modernist) theme, with specific layout/assets overrides to support customisations of that theme.

If considering changing to another theme: for all that is holy, test it locally / on a branch before setting it all on fire...

### To run locally:

`bundle exec jekyll serve`

### To view with draft posts:

Add `--drafts` to the above command

### Automatically publishing posts:

If you include a future timestamp on a post, the post won't get created until that time has passed. Unfortunately that doesn't happen automatically (requires a rebuild of the site in order for the post to be generated). For that reason, there's a GitHub Action which does a daily deployment at 7am UTC; so if you create a blog post with a timestamp of "tomorrow at 1am", it will go live at 7am tomorrow when the action runs. 🪄

### Configuration options

* **To hide the contact CTA in a page footer:** add `hide_contact_cta: true` in front matter
* **To hide a page from the sitemap XML:** add `sitemap: false` in the front matter
* **To display a published date on a static page:** just add `date: <timestamp>` as per blog posts
* **To display a cover image at the top of the post:** add `image: /assets/img/my-header-image.jpg` in the front matter (NB: requires complete relative path so that RSS feed generates correct link)
* **To ensure books have a thumbnail on the [book review page](https://mojovation.co.uk/books):** add `cover: my-book-image.jpg` in the front matter

### Jekyll cheat sheets

[Jekyll docs](https://jekyllrb.com/docs/)  
[Jekyll cheat sheet](https://devhints.io/jekyll)  
[Setting up a GitHub Pages site with Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll)  
[Date formats - strftime](http://www.strfti.me/)