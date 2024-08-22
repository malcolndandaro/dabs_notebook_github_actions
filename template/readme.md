# Starter template for CICD with DABs + Github Actions.

The idea of this demo is to show how we can create a template and with github actions, make it easy to deploy the same code in different environments, like dev, staging and prod.

This demo was inteded to be used with VScode but it can work in any IDE/setup.

-------

***with VScode everything is easier, but we will be going by the command line in this example***

Steps:

0. Clone this repo with git clone
``` 
$ git clone https://github.com/malcolndandaro/dabs_notebook_github_actions
```
1. Create a empty directory with your project name, we are going to use demo_example as the project name.

```
$ mkdir demo_example
```
Now you should have this folder structure:
```

../
    |  dabs_notebook_github_actions
    |  demo_example

```

Now go inside the new folder you just created and turn it into a repo

```
$ cd demo_example
$ git init
```

2. use DABS with the template we just cloned

```
databricks bundle init ../dabs_notebook_github_actions
```
3. Commit on main without any changes
```
git add .
git commit -m "v1"
```

4. Push/Publish your repo to GitHub

5. In your GitHub repo, go into Settings -> Secrets and Variables -> Actions -> New Repository Secret.    
  
Add a new secret with the name: **SP_TOKEN** and the value is a token generated in Databricks: Settings -> Developer -> Access Tokens

5. In your vscode create a new branch with the name dev:
```
git checkout -b dev
````

6. Now you can develop your notebook and commit & push this branch to GitHub. This will trigger the first GitHub action.

7. Create Pull request from dev -> main. This will trigger the second GithHub Action.

8. Approve the PR, this will trigger the final Github Action.