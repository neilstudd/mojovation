### Notes to self

Config currently coded to the [Modernist](https://github.com/pages-themes/modernist) theme, with specific layout/assets overrides to support customisations of that theme.

If considering changing to another theme: for all that is holy, test it locally / on a branch before setting it all on fire...

### To run locally:

`bundle exec jekyll serve`

### To view with draft posts:

Add `--drafts` to the above command

### Configuration options

* **To hide the contact CTA in a page footer:** add `hide_contact_cta: true` in front matter
* **To hide a page from the sitemap XML:** add `sitemap: false` in the front matter
* **To display a published date on a stic page:** just add `date: <timestamp>` as per blog posts

### Jekyll cheat sheets

[Jekyll docs](https://jekyllrb.com/docs/)  
[Jekyll cheat sheet](https://devhints.io/jekyll)  
[Setting up a GitHub Pages site with Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll)  
[Date formats - strftime](http://www.strfti.me/)