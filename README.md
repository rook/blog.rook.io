# blog.rook.io

Redirects [blog.rook.io](https://blog.rook.io) to the Rook blog on Medium at
https://medium.com/rook-io/.

Medium removed their previous support for custom domains (see rook/rook#17938), so this static
Github Pages site is a simple alternative for it.

This site simply performs a client side redirect to https://medium.com/rook-io/ in this priority
order:

1. `location.replace()` in `<head>`
1. `<meta http-equiv="refresh">` fallback for browsers without JavaScript
1. a static link on the page if meta refresh is not supported
