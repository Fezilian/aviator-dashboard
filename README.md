# Aviator phone dashboard

The same numbers as the floating desktop widget, on a phone. Built for an iPhone 13 Pro Max,
works in any phone browser.

How it fits together:

- `docs/index.html` is the page, served by GitHub Pages from this public repository. It holds
  no numbers and no secrets.
- The PC runs `npm run publish` (or `Publish.cmd`) in the Aviator folder. Every minute it
  collects today's figures and, if anything changed, writes them to `data/latest.json` in a
  separate **private** repository (`aviator-feed`) through the GitHub API.
- The phone page reads that file through the API with a read-only fine-grained token that you
  type once. The token and the repository name live only on the phone.

Setup is described in the Aviator USER-GUIDE under "The phone dashboard".
