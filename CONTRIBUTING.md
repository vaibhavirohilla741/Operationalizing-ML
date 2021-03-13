
## 🤝***First time contributing? We will help you out.*** 👍

![GitHub custom open for collaboration](https://img.shields.io/badge/Open%20For-Collaboration-brightgreen?style=for-the-badge)

Refer to the following articles on the basics of Git and Github and can also contact the Project Mentors, in case you are stuck:


- [Getting started with Git and GitHub](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github)
- [Forking a Repo](https://help.github.com/en/github/getting-started-with-github/fork-a-repo)
- [Cloning a Repo](https://help.github.com/en/desktop/contributing-to-projects/creating-a-pull-request)
- [How to create a Pull Request](https://opensource.com/article/19/7/create-pull-request-github)

***If you don't have git on your machine, [install it](https://help.github.com/articles/set-up-git/).***

## 💥 How to Contribute

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)](https://github.com/ellerbrock/open-source-badges/)

- Take a look at the Existing [Issues](https://github.com/vaibhavirohilla741/Operationalizing-ML/issues) or create your own Issues!
- Wait for the Issue to be assigned to you after which you can start working on it.
- Fork the Repo and create a Branch for any Issue that you are working upon.
- Read the [Code of Conduct](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/CODE_OF_CONDUCT.md)
- Create a Pull Request which will be promptly reviewed and suggestions would be added to improve it.
- Add Screenshots to help us know what this Script is all about.



## ⭐HOW TO MAKE A PULL REQUEST:

**1.** Fork [this](https://github.com/vaibhavirohilla741/Operationalizing-ML) repository.
Click on the <a href="https://github.com/vaibhavirohilla741/Operationalizing-ML"><img src="https://img.icons8.com/ios/24/000000/code-fork.png"></a> symbol at the top right corner.

**2.** Clone the forked repository. Open terminal and type:

```bash
git clone https://github.com/<your-github-username>/Operationalizing-ML.git
```

**3.** Navigate to the project directory.

```bash
cd Operationalizing-ML     
```

**4.** Make a feature branch
```bash
git checkout -b <branch-name>

```
**5.** Make changes in source code/ project.

**6.** Stage your changes and commit

```bash
#Add changes to Index
git add .

#Commit to the local repo
git commit -m "<your_commit_message>"
```

**7.** Push your local commits to the remote repo.

```bash
git push origin <brach-name>
```

**8.** Create a [PR](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) !

**9.** **Congratulations!** Sit and relax, you've made your contribution to [Operationalizing-ML](https://github.com/vaibhavirohilla741/Operationalizing-ML) project.


***:trophy: After this, project leaders and mentors will review the changes and will merge your PR if they are found good, otherwise we will suggest the required changes.***

## ADD A REMOTE (UPSTREAM) TO ORIGINAL PROJECT REPOSITORY 
***
Remote means the remote location of project on Github. By cloning, we have a remote called origin which points to your forked repository. Now we will add a remote to the original repository from where we had forked.

```$ cd <your-forked-project-folder>```
```$ git remote add upstream https://github.com/<author-account-username>/<project>.git```
You will see the benefits of adding remote later.

## SYNCHRONIZING YOUR FORK -
***
Open Source projects have a number of contributors who can push code anytime. So it is necessary to make your forked copy equal with the original repository. The remote added above called Upstream helps in this.

```$ git checkout master```
```$ git fetch upstream```
```$ git merge upstream/master```
```$ git push origin master```
The last command pushes the latest code to your forked repository on Github. The origin is the remote pointing to your forked repository on github.

### SQUASHING YOUR COMMITS-
***
You have completed the feature, but you have made a number of commits which make less sense. You should squash your commits to make good commits.

```$ git rebase -i HEAD~5```
This will open an editor which will allow you to squash the commits.

## Style Guides for Git Commit Messages:memo:

#### Here's a list of some good to have points, that can add more value to your contribution logs.

- Use the present tense (example: "Add feature" and not "Added feature")
- Use the imperative mood (example: "Move item to...", instead of "Moves item to...")
- Limit the first line (also called subject line) to 50 characters or less
- Capitalize the subject line
- Separate subject from body with a blank line
- Do not end the subject line with a period
- Wrap the body at 72 characters
- Use the body to explain what, why, vs, and how
- Reference issues and pull requests liberally after the first line

For more detailed reference to the above points, refer here: https://chris.beams.io/posts/git-commit.

## 💥 Issues:
For major changes, you are welcomed to open an issue  about what you would like to contribute. Enhancements will be appreciated.

#### All the Best!🥇

<p align = "center">

<a href="https://github.com/akrish4"><img src="http://ForTheBadge.com/images/badges/built-by-developers.svg" alt="built by developers"></a>
[![built with love](https://forthebadge.com/images/badges/built-with-love.svg)](https://github.com/vaibhavirohilla741/Operationalizing-ML)

</p>
