# blog.rook.io

Redirects [blog.rook.io](https://blog.rook.io) to the Rook blog on Medium at
https://medium.com/rook-io/.

Medium removed their previous support for custom domains (see rook/rook#17938), so this static
Github Pages site is a simple alternative for it.

GitHub Pages serves `index.html` for the root and `404.html` for every other path, which covers the
old custom domain's deep links (e.g. `blog.rook.io/rook-v1-20-storage-enhancements-5331368a5936`).
Both forward the request path unchanged to `https://medium.com/rook-io<path>`, so deep links should
land on their exact article.

The redirect is a client-side `location.replace()`, falling back to `<meta http-equiv="refresh">` and
a static link for browsers without JavaScript. Only the JavaScript path preserves the request path;
the fallbacks send the reader to the publication home.
