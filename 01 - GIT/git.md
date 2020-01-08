
### To create a new repository

1. Prerequisite for this, is that you must have a [github account](https://github.com/). 
2. Once you have created your account, set up a repository.
3. In the upper right corner, next to your avatar, click + and then select **New Repository**. Name your repository *any_project_name*.
4. Write a short description.
5. Select **Initialize this repository with a README**.

### Getting Started - Installing Git

Before you start using Git, you have to make it available on your computer. Even if it’s already installed, it’s probably a good idea to update to the latest version. You can either install it as a package or via another installer, or download the source code and compile it yourself.

### Where to get installer

https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

### Getting a Git Repository

You typically obtain a Git repository in one of two ways:

1. You can take a local directory that is currently not under version control, and turn it into a Git repository

* Create a local folder, for example: front-end-app
* Open a terminal , then, go inside that folder by cd /front-end-app 
* Then, type ``` git init ```. This creates a new subdirectory named .git that contains all of your necessary repository files — a Git repository skeleton.
* git remote add origin https://github.com/ichabondcrane/front-end-app
* git pull origin _branch name_

2. You can clone an existing Git repository from elsewhere.

* Just open a terminal or command prompt and type ``` git clone https://github.com/ichabondcrane/front-end-app ```

That creates a directory named ``` front-end-app ```, initializes a .git directory inside it, pulls down all the data for that repository, and checks out a working copy of the latest version.

### How to commit your local changes

To commit all your local change.

* ``` git add .  ``` This will select files under the current directory. Git will will grab all new or changed files.
* ``` git commit -m "comment on the change done" ```
* ``` git push -u origin _branch name_ ```


### Reference
1. [Github Guide](https://guides.github.com/activities/hello-world/ "Github Guide")
2. [Trainings and Guides](https://www.youtube.com/githubguides)
3. [Getting Started - First Time  Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)