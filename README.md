# P90s Redirects

Hi! This is my bad and ugly attempt to replace YOURLS with something I can host on Github Pages or Cloudflare Pages.\
I ended up using Cloudflare Pages, as I am already using Cloudflare Pages for everything else.

# Usage

Add your own redirects in `redirects.json`.

When using this with Cloudflare Pages, you have to set up a transform rule with the following expression: `(http.request.full_uri wildcard "https://YOURDOMAIN.com*" and http.request.uri.path ne "/redirects.json")`\
This is required, so that Cloudflare serves the content from `YOURDOMAIN.com/` (with the exception of the `redirects.json` file), but in code the path will still look the same (`YOURDOMAIN.com/discord` for example).
