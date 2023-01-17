# Github Pages - built-into-Github website rendering
Github uses Jekyll, a Ruby gem, to render Markdown into a website when `git push`'d to a specific branch and/or directory.

GH Pages is the most general of the 3 tools.

Your website lives at your repo's URL, except with `/pages` inserted after the domain.

### Local authoring story

```
$ cd docs
$ bundle install # Assumes a valid Gemfile, and a ruby in the PATH
$ bundle exec jekyll serve --livereload --open-url
```

Assuming one can get Jekyll up and running locally, it's quite smooth.  The `--livereload` option auto-reloads the browser when changes happen, and `--open-url` pops open the initial browser window for you.

It can be somewhat challenging to build Jekyll on Windows.  The Gemfile is straightforward.  But, you need a Gemfile.  And Ruby.  And sometimes a _config.yml to make your local Jekyll gem happy; some mixtures of Jekyll and gem dependencies don't cleanly handle running in a "docs" sub-directory.


**What about Jekyll-in-Docker?** I was able to get it running, and it's a cool option.  But it requires Docker. I found that choosing the right container for your situation may not be straightforward, and the container may require some tweaking to work the way you'd like it to.

### Publishing story
Configure Github Pages one-time in your repo settings.  For instance, if you have your home page in `docs/index.md` in repo https://github.com/my-org/my-repo, then your site will publish to https://my-org.github.io/my-repo.


After that, just `git push` your markdown changes and wait a few seconds for your updates to appear.

(NOTE: If publishing on [github.com](https://github.com){:target="_blank"}, Github Pages publish requires a paid subscription **unless your repo is public**). 

### GH Pages examples

- [This Review](https://walquis.github.io/authoring-tools/){:target="_blank"}, and [Markdown source](https://github.com/walquis/authoring-tools/){:target="_blank"}

