# my-sites

Frontend multi-site workspace where each site is an independent top-level folder and the active hosted site is selected from YAML.

## Structure

- `anniversary/`: complete codebase for the anniversary site
- `experiment/`: complete codebase for the experiment site
- `active-site.yaml`: controls which site GitHub Pages deploys

## Switch active site

1. Edit `active-site.yaml`
2. Set:

```yaml
active_site: anniversary
```

Use a top-level folder name from this repository (for example `anniversary` or `experiment`).

## Local preview (before pushing)

Open any site directly in your browser:

- Right-click `anniversary/index.html` and choose open in browser
- Right-click `experiment/index.html` and choose open in browser

This is independent from deployment selection in `active-site.yaml`.

## GitHub hosting behavior

This repository includes a GitHub Actions workflow (`.github/workflows/deploy-active-site.yml`) that deploys the top-level folder selected in `active-site.yaml` to GitHub Pages.

To switch the live hosted site:

1. Change `active_site` in `active-site.yaml`
2. Commit + push to `main`
3. GitHub Actions redeploys using `<active_site>/`

If the selected folder does not exist, deployment fails with a clear error.

## Adding a new site

1. Create a top-level folder like `new-site/`
2. Put your frontend files inside it
3. Set `active_site: new-site` in `active-site.yaml`
4. Commit + push
