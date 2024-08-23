# Starter Template for CI/CD with DABS + GitHub Actions

The purpose of this demo is to show how to use a bundle template and GitHub Actions to easily deploy the same code to different environments, such as development, staging, and production.

Official docs about DABS Template: [DABS template docs](https://docs.databricks.com/en/dev-tools/bundles/custom-bundle.html)

This demo is intended to be used with VSCode, but it can work in any IDE/setup.

-------

***With VSCode, everything is easier, but in this example, we will be using the command line.***

## Steps:

1. **Clone this repo with `git clone`:**
    ```bash
    git clone https://github.com/malcolndandaro/dabs_notebook_github_actions
    ```

2. **Create an empty directory with your project name (we will use `demo_example` as the project name):**
    ```bash
    mkdir demo_example
    ```

    Now you should have this folder structure:
    ```text
    ../
        |  dabs_notebook_github_actions
        |  demo_example
    ```

3. **Go inside the new folder you just created and turn it into a repo:**
    ```bash
    cd demo_example
    git init
    ```

4. **Use DABS with the template we just cloned:**
    ```bash
    databricks bundle init ../dabs_notebook_github_actions
    ```

5. **Commit on `main` without any changes:**
    ```bash
    git add .
    git commit -m "v1"
    ```

6. **Push/Publish your repo to GitHub.**

7. **In your GitHub repo, go to `Settings -> Secrets and Variables -> Actions -> New Repository Secret`:**  
    Add a new secret with the name: **`SP_TOKEN`** and the value as a token generated in Databricks:  
    `Settings -> Developer -> Access Tokens`

8. **In your VSCode, create a new branch with the name `dev`:**
    ```bash
    git checkout -b dev
    ```

9. **Now you can develop your notebook, commit, and push this branch to GitHub. This will trigger the first GitHub Action.**

10. **Create a Pull Request from `dev` to `main`. This will trigger the second GitHub Action.**

11. **Approve the PR, which will trigger the final GitHub Action.**
