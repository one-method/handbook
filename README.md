# OneMethod Handbook

This is the OneMethod handbook repository. For info on how to contribute to the handbook, refer to the [How To Contribute page](https://one-method.github.io/handbook/how-to-contribute/)


The OneMethod handbook is a Git versioned handbook, similar to GitLab's handbook. Unlike GitLab's handbook, this handbook is built using mkdocs and hosted in GitHub pages for simplicity. There is no web editor, so changes must be made through GitHub or locally via an IDE or text editor.

## Project Info

The handbook is built using MKDocs with the default mkdocs theme, and uses github pages to host the static site that is generated.

The wiki is hosted on github pages here: https://one-method.github.io/handbook/

It is built using the python library [mkdocs](https://www.mkdocs.org/)

The theme being used is `mkdocs`


## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server for local development.
* `mkdocs build` - Build the documentation site. Create static web assets to deploy
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.


## Deployment

GitHub actions is used to deploy the static site to GitHub pages. 
1. When main is pushed to, the `mkdocs build` command is run. 
2. The result of the build, the static website assets, is pushed into the gh-pages branch. 
3. The gh-pages branch, now containing the static website assets, is automatically deployed to GitHub pages where the website can be viewed.

## Local Development

### 1. Install MkDocs
- MkDocs requires Python, so ensure you have Python installed.
- Install MkDocs using pip.
    ```bash
    pip install mkdocs
    ```
### 2. **Build and Serve Locally:**
   - Preview your site locally.
     ```bash
     mkdocs serve
     ```
   - This will start a local server at `http://127.0.0.1:8000`.

