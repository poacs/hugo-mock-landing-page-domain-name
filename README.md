# hugo-mock-landing-page-autodeployed

## Purpose of the Deployment Workflow

The primary goal of the `gh-pages-deployment.yaml` workflow is to streamline continuous integration and deployment (CI/CD) for this Hugo site. By leveraging GitHub Actions, the workflow compiles the static pages and publishes them to the `gh-pages` branch.

## Workflow Steps

1. **Checkout**  
   Uses `actions/checkout@v3.5.1` to clone the repository and fetch all submodules to ensure Hugo themes or external dependencies are included.

2. **Initialize Hugo**  
   Uses `peaceiris/actions-hugo@v2.6.0` to install a specific version of Hugo to prepare the build environment on the GitHub runner.

3. **Compile the Site**  
   Runs the `hugo` command to generate static files.

4. **Publish to GitHub Pages**  
   Uses `peaceiris/actions-gh-pages@v3.9.3` to push the static content to the `gh-pages` branch.

## Insights from Claude

I used Claude for a line-by-line explanation of the GitHub Actions .yaml file. I was helped with:
- Why `fetch-depth: 0` is needed to generate `.GitInfo` and `.Lastmod` in Hugo.
- How `secrets.GITHUB_TOKEN` works with GitHub Actions, including necessary permissions for writing to the `gh-pages` branch.
- Common pitfalls/deployment failures

## Live Site URL

**[https://poacs.github.io/hugo-mock-landing-page-autodeployed/](https://poacs.github.io/hugo-mock-landing-page-autodeployed/)**

---

Refer to [GitHub Actions documentation](https://docs.github.com/en/actions) and [Hugo’s official docs](https://gohugo.io/documentation/) for more information.
