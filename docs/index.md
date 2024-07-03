# Welcome to MkDocs

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.


## Writing Docs

https://www.mkdocs.org/user-guide/writing-your-docs/



## Setup

Creating a self-hosted, Git versioned handbook similar to GitLab's handbook can be achieved with a combination of Git for version control, a static site generator for building the site, and a web server for hosting it. Here’s a simple way to get started:

### 1. Set Up Your Git Repository

1. **Initialize a Git Repository:**
   - Create a new directory for your handbook and initialize a Git repository.
     ```bash
     mkdir my-handbook
     cd my-handbook
     git init
     ```

2. **Add a Remote Repository:**
   - If you want to host your repository on a platform like GitHub, GitLab, or a self-hosted Git server, add the remote URL.
     ```bash
     git remote add origin <remote-repo-url>
     ```

### 2. Choose a Static Site Generator

Static site generators like Jekyll, Hugo, or MkDocs can transform your Markdown files into a static website. MkDocs is particularly suitable for documentation purposes.

#### Using MkDocs

1. **Install MkDocs:**
   - MkDocs requires Python, so ensure you have Python installed.
   - Install MkDocs using pip.
     ```bash
     pip install mkdocs
     ```

2. **Create a New MkDocs Project:**
   - Initialize a new MkDocs project in your handbook directory.
     ```bash
     mkdocs new .
     ```

3. **Edit `mkdocs.yml`:**
   - This is the configuration file for your MkDocs project. Customize it according to your needs, such as changing the site name or theme.

4. **Add Your Content:**
   - Add Markdown files to the `docs` directory. For example, create an `index.md` file as the homepage.
     ```markdown
     # Welcome to My Handbook
     
     This is the homepage of the handbook.
     ```

5. **Build and Serve Locally:**
   - Preview your site locally.
     ```bash
     mkdocs serve
     ```
   - This will start a local server at `http://127.0.0.1:8000`.

### 3. Set Up Automated Deployment

You can automate the deployment of your MkDocs site using Git hooks or CI/CD pipelines. For instance, GitHub Pages or GitLab Pages can automatically deploy your site whenever you push changes to your repository.

#### Using GitHub Pages

1. **GitHub Actions Workflow:**
   - Create a GitHub Actions workflow file `.github/workflows/deploy.yml`.
     ```yaml
     name: Deploy MkDocs site

     on:
       push:
         branches:
           - main  # or the branch you want to deploy from

     jobs:
       deploy:
         runs-on: ubuntu-latest

         steps:
           - name: Checkout repository
             uses: actions/checkout@v2

           - name: Set up Python
             uses: actions/setup-python@v2
             with:
               python-version: '3.x'

           - name: Install MkDocs and dependencies
             run: |
               pip install mkdocs

           - name: Deploy to GitHub Pages
             run: |
               mkdocs gh-deploy --force
             env:
               GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
     ```

2. **Commit and Push:**
   - Commit your changes and push them to GitHub.
     ```bash
     git add .
     git commit -m "Set up MkDocs site"
     git push origin main
     ```

### 4. Host Your Handbook

Once your site is built and deployed, it will be accessible via the URL provided by your hosting service (e.g., `https://<username>.github.io/<repo>` for GitHub Pages).

### Summary

- **Set up a Git repository** to version your handbook.
- **Choose a static site generator** like MkDocs.
- **Create your content in Markdown** files.
- **Build and serve your site locally** to preview changes.
- **Automate deployment** using GitHub Actions, GitLab CI/CD, or another CI tool.
- **Host your site** using GitHub Pages, GitLab Pages, or a similar service.

By following these steps, you can create a self-hosted, Git versioned handbook with ease.

### 5. Setup GitHub pages settings

Once the action has deployed successfully once - In the repository on github, go to settings > pages. Under Build and deployment, select source as "Deploy from a branch". Then select gh-pages as your branch and choose the root folder. Then press save. This will serve the github pages content from the gh-pages branch.


