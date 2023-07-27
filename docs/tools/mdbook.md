# mdbook - Book authoring tool used by the Rust programming language project

Specifically for authoring content with chapters.

Easy to use, lightweight, straightforward local authoring and publishing stories.

### Local authoring story

One-time: [Download and install](https://rust-lang.github.io/mdBook/guide/installation.html){:target="_blank"} a single prebuilt executable for your architecture, and put it in your PATH.

The Table-of-Contents format is somewhat rigid. 

Although mdbook [doesn't support linking to sections in a chapter file from the summary, forcing each section into a separate file](https://github.com/rust-lang/mdBook/issues/167){:target="_blank"}, there are workarounds involving redirects that accomplish the desired effect (see the [object.md](https://github.com/walquis/react-study-book/blob/main/src/es6/destructuring/object.md) source, which redirects to a section in the parent `destructuring` chapter).   This makes re-organizing a chapter unnecessarily onerous.  In addition, it forces each section into a separate (and potentially artificially small) page.

```
$ mdbook serve  # builds, watches for changes, refreshes local browser on change.
```
A `book.toml` defines a handful of other metadata.
Chapter layout (i.e. table of contents) is defined in `SUMMARY.md`.

### Publishing story
Basically, publish can be just Github Pages; GH Pages understands mdbook's output, since it's just static HTML/CSS.

1. Configure `book.toml` to output the build to `docs` directory.
1. Point your repo's Github Pages settings to `docs`.
1. `git add/commit/push` the `mdbook build` output (that is, `docs`) to Github.
1. Github Pages renders it with a default Github Action.
1. View it at https://<org>.github.io/<repo>

### MDBook examples
- [Chris's Git Basics Course](https:/walquis.github.io/git-basics-team-project) - and [Markdown source](https://github.com/walquis/git-basics-team-project/tree/main/thebook){:target="_blank"}
- [Chris's React Study Notes](https://walquis.github.io/react-study-book/){:target="_blank"} - and [Markdown source](https://github.com/walquis/react-study-book/){:target="_blank"}
- [MDBook Documentation](https://rust-lang.github.io/mdBook/){:target="_blank"} - and [Markdown source](https://github.com/rust-lang/mdBook/tree/master/guide){:target="_blank"}

