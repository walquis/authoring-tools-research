# Google Codelabs
A guided, tutorial, hands-on experience.  Wraps some search, navigation, categories, etc. around a Google Docs page. Markdown is also supported.

Presentation of material is the "Codelabs" way.  Codelabs are arranged as a list of cards\--one card per Codelab\--that can be searched and filtered.

The [Codelab Formatting Guide] is full of bells and whistles activated by very particular Google-Doc-specific formatting.  For instance:
```
In order to include a survey question in your codelab, add a single-cell table with a light blue 3 background.
```

### Local authoring story

Download claat, a single Go binary (unless you have Apple ARM silicon; in that case, you may need to install Go and build it).

Arrange your content, run `claat export` to generate the static site.
```
$ cd site/codelabs
$ claat export git-basics.md
```
In another terminal, `gulp serve` to serve it.
```
$ cd site
$ gulp serve --codelabs-dir=codelabs
```
If you don't want to keep re-running `claat export`, you can install `grip`, which renders a single Markdown page:
```
$ brew install grip   # (Mac-specific install cmd)
$ cd site/codelabs
$ grip git-basics.md --browser  # Opens a browser tab, and auto-refreshes on change
```

To propagate changes, it's necessary to re-run the `claat export`.  (`gulp` has tasks that appear to support live reload, but I wasn't able to get them to work for me).

As far as writing and using codelabs, I haven't done much yet with this format.

### Publishing story

The `claat export`'d content needs to be published to a Codelabs website (I made a Dockerfile and a Kubernetes deploy for this purpose).

From there, it's not that far to "commit-to-deploy", but does require some extra steps.

### Google Codelabs examples
- [Google Codelabs](https://codelabs.developers.google.com/){:target="_blank"} 
- [Solace.dev Codelabs](https://codelabs.solace.dev/){:target="_blank"} 
- [Chris's Alpha-version Under-Construction Codelabs Site](https://codelabs.walquist.net){:target="_blank"}  - (View in incognito 'til I fix document.write issue) - and [Repo with source](https://github.com/walquis/codelab-example){:target="_blank"} 
