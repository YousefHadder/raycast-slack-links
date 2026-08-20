# Slack Link Formatter

Convert a URL on your clipboard into a rich title hyperlink that pastes cleanly into Slack.

## How It Works

1. Copy a URL.
2. Run **Copy Slack Link from Clipboard URL** in Raycast.
3. Paste into Slack.

The command fetches the page title, then writes two clipboard representations:

- Plain text: the raw URL
- HTML: an anchor tag whose visible text is the page title

Slack prefers the HTML representation and shows a clickable title hyperlink. Apps that only support plain text receive the original URL.

## GitHub Links

For GitHub pull requests and issues, the command first tries to use the GitHub CLI (`gh`) to fetch the title when `gh` is installed and authenticated. This helps with links that do not expose complete page metadata to unauthenticated requests.

If `gh` is unavailable or the lookup fails, the command falls back to fetching the page HTML directly.
