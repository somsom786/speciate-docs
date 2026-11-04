# Publish SPECIATE documentation to GitBook

This file is a setup guide and intentionally is **not** listed in the public GitBook navigation.

## 1. Create a dedicated GitHub repository

Suggested name: `speciate-docs`. Do not place SPECIATE documentation inside an unrelated code project.

1. Visit https://github.com/new and create the repository. Choose public visibility if the docs should be publicly accessible.
2. Extract the supplied ZIP locally and upload **all extracted files and folders**, including the hidden `.gitbook.yaml` file, to the repository root.
3. Commit the changes to the `main` branch.

You may also use Git locally:

```bash
git init
git add .
git commit -m "docs: initial SPECIATE GitBook documentation"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/speciate-docs.git
git push -u origin main
```

## 2. Connect GitBook

1. Create a GitBook site/space or open an existing one.
2. In the space, choose **Set up Git Sync**.
3. Authorize GitBook's GitHub app for the new repository (this authorization is independent of the ChatGPT GitHub connection).
4. Select `speciate-docs`, branch `main`, and repository root `/`.
5. **Choose GitHub → GitBook** for the initial sync, to import the existing Markdown rather than overwrite it.
6. Review the page tree against `SUMMARY.md`, check images/links, and publish the site using GitBook's current publish controls.

GitBook official guide: https://gitbook.com/docs/guides/editing-and-publishing-documentation/import-or-migrate-your-content-to-gitbook-with-git-sync

GitBook configuration reference: https://gitbook.com/docs/getting-started/git-sync/content-configuration

## 3. Check before publishing

- Check all 14 navigation links resolve.
- Check the first-page status notice is visible.
- Verify no real-money execution or onchain deployment is presented as already live.
- Verify the public link on mobile.
- Add official website, social, GitHub organization, and support links **only when confirmed**.
- Ensure the documentation site is explicitly published; Git Sync alone is not proof it is public.

## 4. Ongoing updates

PRs to the docs repo become the reviewable source of truth for GitBook Git Sync. Track major technical changes and update the docs in the same PR where possible.
