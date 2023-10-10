# DIL Manual GitHub page source

This website uses a Jekyll template. The github.io page is automatically updated whenever pull requests are merged into this branch.

## Building and previewing your site locally

When rendering locally you need to manually "turn off" the option of using `remote_theme` and just use `theme` instead in `_config.yml`.
Assuming Jekyll and Bundler are installed on your computer:

1.  Change your working directory to the root directory of your site.

2.  Run `bundle install`.

3.  Run `bundle exec jekyll serve` to build your site and preview it at `localhost:4000`.

    The built site is stored in the directory `_site`.

----

- Jekyll: https://jekyllrb.com
- Just the Docs: https://just-the-docs.github.io/just-the-docs/
- GitHub Pages: https://docs.github.com/en/pages
- Bundler: https://bundler.io
