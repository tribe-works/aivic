# AiVic Static Site

Static deploy source for https://aivic.ca/.

## cPanel Git Version Control setup

1. Create/connect this repository in cPanel **Git Version Control**.
2. Repository path should be outside the live document root when possible, e.g.:
   `/home/hwvucjaext/repositories/aivic-static-site`
3. Branch: `main`.
4. Deployment uses `.cpanel.yml` to copy files into:
   `/home/hwvucjaext/aivic.ca/`
5. After pulling in cPanel, click **Deploy HEAD Commit**.
6. Verify:
   - https://aivic.ca/
   - https://aivic.ca/ai-tools/
   - https://aivic.ca/sitemap.xml

## Local source

This repo contains only deployable static files, not the full SeanOS folder.
