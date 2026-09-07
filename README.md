# Aviator phone dashboard

The same numbers as the floating desktop widget, on a phone. Built for an iPhone 13 Pro Max,
works in any phone browser.

How it fits together:

- `public/index.html` is the page. GitLab Pages serves it. It holds no data and no secrets.
- The PC runs `npm run publish` (or `Publish.cmd`) in the Aviator folder. Every minute it
  collects today's figures and, if anything changed, writes them to `data/latest.json` in this
  project through the GitLab API. That is a small commit per update; no pipeline runs for it.
- The phone page reads `data/latest.json` through the API with a read-only project token that
  you type once. The token and the project path live only on the phone.

The project is private. Nobody without a token sees the numbers.

Setup is described in the Aviator USER-GUIDE under "The phone dashboard".
