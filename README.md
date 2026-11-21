# The Lab — GitHub Pages website

A minimalist dark editorial website with a fixed left sidebar, Stream Tech category, article search, article images, reading-time estimates and a browser-based publishing dashboard.

## 1. Publish the website on GitHub Pages

1. Create a GitHub repository. For the simplest URL, name it `YOUR-USERNAME.github.io`.
2. Upload **all files and folders** from this package to the repository root. Keep the folder structure intact.
3. In GitHub, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then Save.
6. Wait for the deployment to finish. Your site will be at `https://YOUR-USERNAME.github.io/`.

For a repository with another name, the site URL will usually be `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`. The relative links in this site support that setup too.

## 2. Connect the article dashboard

Open `https://YOUR-SITE-URL/admin/`.

Create a fine-grained personal access token:
1. Visit https://github.com/settings/personal-access-tokens/new
2. Set **Resource owner** to your GitHub account.
3. Under **Repository access**, choose **Only select repositories**, then select this website repository.
4. Under **Repository permissions**, set **Contents** to **Read and write**. Metadata read access is normally included automatically.
5. Generate the token and copy it.

In the dashboard, enter your GitHub username, repository name, branch (`main` by default), and token. Click Connect. Write an article, optionally select a cover image, and publish.

The token is held in this browser tab's `sessionStorage`; it is not committed to the repository. Disconnect when you finish and close the tab. Do not use a broad classic token or share the token.

## 3. Writing articles

- The editor accepts Markdown.
- Use `## Heading` for section headings, `**bold**`, `- item` for lists, and fenced code blocks for code.
- Cover images must be 5 MB or smaller.
- Publishing commits the Markdown article, any cover image, and the updated `articles.json` index to your repository.
- GitHub Pages then rebuilds the public site. Changes may take a minute or two to appear.
- Reading time is estimated at 200 words per minute.

## Important limitations and security

GitHub Pages is static hosting. The dashboard uses a GitHub fine-grained token in the browser to commit content to the repository. This is convenient for a personal site, but anyone who can use your unlocked editor session can publish to your repository within the token's permissions. Keep the token private, restrict it to this one repository, and disconnect after editing.

Published content and images are public. This starter dashboard supports creating and updating articles; it does not yet include deletion, multiple editor accounts, drafts, or server-side authentication. The public site loads Markdown rendering libraries from jsDelivr and fonts from Google Fonts, so those enhancements require an internet connection.

## Files

- `index.html` — homepage and article search
- `article.html` — article reading page
- `articles.json` — public article index
- `articles/` — Markdown article content
- `admin/` — publishing dashboard
- `assets/` — styles, scripts and uploaded images
