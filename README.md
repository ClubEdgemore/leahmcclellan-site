# Leah McClellan: product portfolio

A plain HTML site. There is no build step and no framework. Edit the files, commit, and GitHub publishes it.

```
index.html          the whole page (text, layout, links)
assets/             images used on the page
  cfb-home.png      Saturday is for CFB home screen
  alibi-logo.png    Alibi Murder Mysteries logo
.nojekyll           tells GitHub to publish the files as-is
```

## Editing it yourself

**Change text or links**
1. On GitHub, open `index.html` and click the pencil icon (Edit this file).
2. Press Ctrl+F (Cmd+F on Mac) and search for the words you want to change. Edit them.
3. Click **Commit changes**. The live site updates in about a minute.

Each section starts with a capitalized marker (NAV, HERO, PRODUCT 1, PRODUCT 2, CASE STUDIES, and so on), so you can search for it to jump to that section. Only change the words between the `>` and `<` characters, and leave the tags alone.

**Change the accent color:** at the top of `index.html`, change the color code in `--accent: #FF6A2B;`. It updates everywhere.

**Swap a screenshot:** upload a new image to the `assets` folder with the **same file name** (Add file, then Upload files). It replaces the old one automatically. Phone screenshots look best at about 600 px wide.

**Add a new section or product:** copy an existing section block from its comment to the end of its section, paste it below, and edit the copy. Or ask Claude to do it and paste the result in.

## Publishing on GitHub

1. Create a free GitHub account and a new **public** repository (for example `portfolio`).
2. Click **Add file, then Upload files**. Drag in `index.html`, `.nojekyll`, and the `assets` folder. Commit.
3. Go to **Settings, then Pages**. Under "Build and deployment," choose **Deploy from a branch**, branch **main**, folder **/ (root)**. Save.
4. After a minute your site is live at `https://YOUR-USERNAME.github.io/portfolio/`. Check it there first.

## Switching leahmcclellan.design from WordPress

Do this only after the page looks right at the github.io address.

**Read this first: your case studies are still on WordPress.** The case study cards link to pages like `leahmcclellan.design/epic-homepage-holiday-improvements/`. If you point the domain at GitHub, those pages stop working. Pick one before you switch:
- **Move them.** Recreate each case study as its own page in this repo (for example `epic-homepage.html`), then update the links in `index.html`. Ask Claude to build them from your existing text.
- **Keep WordPress on a subdomain.** For example, `archive.leahmcclellan.design`, then update the links to match.

**Don't break your email.** `me@leahmcclellan.design` depends on MX records in your DNS. Only add or change the website records below, and leave the MX records alone.

**Steps** (GitHub's current instructions are in the docs page "Managing a custom domain for your GitHub Pages site"):
1. In the repo go to **Settings, then Pages, then Custom domain**. Enter `leahmcclellan.design` and click Save. Do this before changing DNS.
2. Where your domain's DNS is managed, remove the old WordPress website records. If the domain is registered through WordPress.com, this is under **Domains, then DNS records**.
3. Add four **A records** for the root domain (`@`), pointing to GitHub:
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
4. Add a **CNAME record** for `www` pointing to `YOUR-USERNAME.github.io`.
5. Back in Settings, then Pages, tick **Enforce HTTPS** once it becomes available. This can take up to a day.

DNS changes can take anywhere from minutes to a day to spread. During that time some visitors will still see the old WordPress site.
