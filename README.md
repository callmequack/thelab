# The Lab — GitHub Pages website

A minimalist dark editorial website with a fixed left sidebar, three article categories (Stream Tech, Speedruns and Resources), article search, cover images, reading-time estimates and a browser-based publishing dashboard.

## Website

The site is hosted from this repository using GitHub Pages. Its current project URL is:

https://callmequack.github.io/thelab/

## Article editor

Open https://callmequack.github.io/thelab/admin/ and connect using a fine-grained GitHub personal access token.

Create a token at https://github.com/settings/personal-access-tokens/new:
1. Set the resource owner to your GitHub account.
2. Choose **Only select repositories** and select **thelab**.
3. Set **Contents** permission to **Read and write**.
4. Generate and copy the token.

The editor is prefilled with the repository owner, repository name and main branch. Paste the token and connect. The token is held in this browser tab's session storage and is not committed to the repository. Disconnect when finished and close the tab.

## Publishing and managing articles

- Write article content in Markdown.
- Choose one of the categories: **Stream Tech**, **Speedruns** or **Resources**.
- Optionally add a cover image up to 5 MB.
- Publish new articles or edit existing ones from the editor.
- Use **Delete** beside a published article to remove it from the public index and delete its Markdown file. The editor asks for confirmation first.
- Uploaded cover images are intentionally retained when an article is deleted, because an image might be shared by another article.
- GitHub Pages may take a minute or two to reflect a commit.

## Security and limitations

GitHub Pages is static hosting. The dashboard uses a GitHub fine-grained token in the browser to commit content to the repository. Anyone with access to your unlocked editor session can use the token within its repository permissions. Keep it private, restrict it to this repository, and disconnect after editing.

Published content and images are public. The editor does not provide server-side authentication or multiple editor accounts. The public site loads Markdown rendering libraries from jsDelivr and fonts from Google Fonts, so those enhancements require an internet connection.

## Main files

- `index.html` — homepage, category navigation and search
- `article.html` — article reading page
- `articles.json` — public article index
- `articles/` — Markdown article content
- `admin/` — publishing dashboard
- `assets/` — styles, scripts and uploaded images
