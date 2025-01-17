# gopkg

A Caddy plugin to add gopkg-like functionality to your own web sites.

# Usage

`gopkgr [path] [repo-uri]`

`gopkgr [path] [vcs] [repo-uri]`

```
zikes.me {
  // default vcs is git
  gopkgr /multistatus https://github.com/zikes/multistatus
  gopkgr /github/([\w\-\.]+)/([\w\-]+) https://github.com/$1/$2

  // use mercurial
  gopkgr /myrepo hg https://bitbucket.org/zikes/myrepo
}
```

The above would make the repos go get-able via `go get zikes.me/chrisify`,
`go get zikes.me/myrepo`, and `go get zikes.me/multistatus`.

If the urls are visited normally the browser will be redirected to the repo uri.

Once implemented, `go get` can enforce your import paths with
[import path checking](https://golang.org/cmd/go/#hdr-Import_path_checking).
