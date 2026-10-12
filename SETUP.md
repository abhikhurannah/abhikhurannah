# Publish your GitHub profile

Create an empty **public** repository named `abhikhurannah` under your `abhikhurannah` account. Do not initialize it with a README, license, or gitignore.

```sh
cd /Users/abhaykumar/Downloads/abhikhurannah-profile
git init -b main
git add README.md SETUP.md .gitignore .github/workflows/contribution-art.yml
git commit -m "Set up GitHub profile and contribution visuals"
git remote add origin https://github.com/abhikhurannah/abhikhurannah.git
git push -u origin main
```

Use your GitHub credential manager or a personal access token if prompted for HTTPS authentication.

If the repository already has commits, clone it into another folder and copy these files (including `.github`) into that clone before committing and pushing to preserve its history.

## Contribution visuals

The workflow runs on the first push to `main`, README or workflow changes, manual dispatch, and daily at 02:23 UTC (07:53 IST). Scheduled runs can be delayed.

Open **Actions → Generate contribution visuals** after pushing. The 3D job commits `profile-3d-contrib/` to the default branch; the snake job publishes to the `output` branch. Refresh your profile after both jobs succeed. Images appear after their first successful generation.

The workflow uses the automatic `GITHUB_TOKEN` and declares `contents: write`; no custom secrets are needed. If publishing fails, check **Settings → Actions → General** and any repository or organization rules that prevent workflow commits, then retry with **Run workflow**.

## Later updates

Pull the generated calendar commit before editing locally:

```sh
git pull --rebase
# Edit your profile files.
git add README.md SETUP.md .gitignore .github/workflows/contribution-art.yml
git commit -m "Update GitHub profile"
git push
```

Third-party stats cards can be throttled. Contribution visuals reflect GitHub activity. Verify personal claims and project links before publishing.
