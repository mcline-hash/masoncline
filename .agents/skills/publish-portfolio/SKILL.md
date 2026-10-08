---
name: publish-portfolio
description: >-
  Use this skill when Mason wants to deploy, upload, or push portfolio updates and changes directly to GitHub so that changes reflect live on masoncline.com.
---

# Publish Portfolio Skill

Follow this runbook to package and push updates from the local `WEBSITE` directory to GitHub (`mcline-hash/masoncline`), triggering automatic deployment to `masoncline.com`.

## 1. Prerequisites
- Remote URL: `https://github.com/mcline-hash/masoncline.git`
- Target branch: `main`
- Live URL: `masoncline.com` (pointed through GitHub Pages custom CNAME `masoncline.ca`)

---

## 2. Pre-Flight Checks
Before pushing to production:
1. Verify `index.html` has valid markup (no broken tags or misplaced brackets).
2. Check that all referenced images exist in their designated folders.
3. Check that external media links (YouTube embeds, Vimeo, Instagram) are valid and functional.
4. Verify `CNAME` file exists with `masoncline.ca` so GitHub Pages maintains custom domain routing.
5. **Archive Version:** Duplicate the updated `index.html` into `versions/indexV[X.X].html` and log the update in `versions/README.md`.

---

## 3. Git Push Workflow
When Apple Command Line Tools / Git is active:

1. Stage all changed files:
   ```bash
   git add .
   ```
2. Check status:
   ```bash
   git status
   ```
3. Commit with a concise, professional message:
   ```bash
   git commit -m "Update portfolio: [Description of project or fix]"
   ```
4. Push to GitHub:
   ```bash
   git push origin main
   ```

---

## 4. Alternate Deployment via GitHub API (Direct Sync)
If git CLI is unavailable, files can be updated or uploaded directly to the GitHub repository using the GitHub Contents API with the authenticated personal access token:
```bash
curl -X PUT \
  -H "Authorization: token <PAT>" \
  -H "Accept: application/vnd.github.v3+json" \
  https://api.github.com/repos/mcline-hash/masoncline/contents/<path> \
  -d '{"message":"Update <file>","content":"<base64-content>","sha":"<blob-sha>"}'
```
