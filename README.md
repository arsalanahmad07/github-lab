# Git and GitHub

## Motivation
Following is a very simplified one-liner answer to common questions. There is much more detail into each question and students are encouraged to research the topic on their own.

#### What is Git?
Git is a version control software/application that keeps track of the history of your changes.

#### Why Git?
Git keeps track of the history of your project and allows you to make 'checkpoints' seamlessly as you develop your code. It makes collaborative work on a project go from a nightmare to a smooth, painless experience as you don't need to email 10 different versions of your project each time someone makes a new change in source code.

#### Difference between Git and GitHub?
- Git is an application/software that tracks your changes.

- GitHub is an online platform for hosting Git repositories allowing every one in your team to access your code.

#### Local repository vs. Remote repository
- Local repository is the version of the project downloaded in your local machine. 
- Remote repository is the version of the project uploaded on an online hosting platform that anyone in your collaborative team can download.

> Git is not the only version control system. Other examples include Mercurial, Apache Subversion etc. Likewise there are many alternatives to GitHub.com including GitBucket, GitLab, Bitbucket, Sourceforge etc. But by far, Git and GitHub have become the De facto standard for version controlling and collaborative work.

## Basic Git Commands
The following are basic git commands you need to get started. Keep in mind the following is a very high-level description of each command's functionality. In reality, there is much more to each command which you can learn from reading the documentation hyperlinked to each command's heading. For now, a purposefully simplified description of each command can suffice.

* [git help](https://git-scm.com/docs/git-help): Redirects you to the manual page of a specified git command. 
  * `USAGE: git help <sub_command>`
  
* [git clone](https://git-scm.com/docs/git-clone): Download the latest version of a remote repository.
  * `USAGE: git clone <remote_repo_url>`
  
* [git checkout](https://git-scm.com/docs/git-checkout): Switch between branches.
  * `USAGE: git checkout [OPTIONS] <branch_name>`
    * -b: Create a new branch
    
* [git branch](https://git-scm.com/docs/git-branch): List all branches in the local repository.
  * `USAGE: git branch [OPTIONS]`
    * --delete: Delete a branch `e.g. git branch --delete update-docs`
    
* [git add](https://git-scm.com/docs/git-add): Propose changes for next commit.
  * `USAGE: git add <path_to_file>`
     * `git add .`: Recursively add all files as changes for next commit.
     
* [git status](https://git-scm.com/docs/git-status): Display state of your working repository.
  * `USAGE: git status [OPTIONS]`
    * -s: Display a short status
    
* [git commit](https://git-scm.com/docs/git-commit): Save a snapshot of working directory.
  * `USAGE: git commit [OPTIONS]`
    * -m: Specify a commit message
    * -a: Skip the staging area (commit without using git add first)
    
* [git push](https://git-scm.com/docs/git-push): Upload your commit from local repository to repote repository
  * `USAGE: git push`
  
* [git fetch](https://git-scm.com/docs/git-fetch): Get all updates from the repote repository.
  * `USAGE: git fetch`
  
* [git merge](https://git-scm.com/docs/git-merge): Download updates from git fetch command into your local repository.
  * `USAGE: git merge`
  
* [git pull](https://git-scm.com/docs/git-pull): Combination of git fetch and git merge.
  * `USAGE: git pull`

## Getting started 
Learn more about Installation procedure [here](#installation--setting-up-git-environment). The following set of commands are executed in `Git Bash`.

### Create a repository
1) Head on over to https://github.com/new and create a new private repository. Tick the checkbox `Add a README.md file`.
2) Clone the remote repository by copying the URL of the newly created repository and use the command `git clone <remote_repo_url>`.
3) A local repository has been created in the present working directory.

### Making your first commit
1) Open the cloned repository through `cd <repo_name>`.
2) Open the repository in file explorer `explorer.exe .`.
3) Create a new file hello.txt and add some dummy text inside it. 
4) Track hello.txt to be added in next commit `git add hello.txt`.
5) Commit/Save changes to the local repository `git commit -m "Add hello.txt"`.
6) Update GitHub (remote) repository with the changes made in local repository. `git push`. 

### Commit message etiquettes 
- [Write good commit messages](https://cbea.ms/git-commit/)
- [An example repository with good commit messages](https://github.com/chocolatey/choco/pulls?q=is%3Apr+is%3Aclosed)

### Branches
Branches are one of the most powerful concepts in Git that makes collaborative work seamless. A branch represents an independent line of development. 

1) Create a branch `git branch <branch_name>`.
2) Update the current branch through `git checkout <branch_name>`. Observe which branch you're in through the command `git branch`.

> A shortcut to do both of these steps in one command is `git checkout -b <branch_name>` which both creates a new branch and updates the current branch.

3) Create a new file `foo.txt` and add some dummy text.
4) Commit the creation of foo.txt through the command `git commit -am "Add foo.txt"`. (-a flag is used to skip `git add` step)
5) You now have commited creation of foo.txt in your newly created branch. However, as branches represent independent line of development, this change is only visible in the new branch and not in the default branch.
6) Update the current branch to `main` / `master` through `git checkout main` or `git checkout master`.
7) Observe you do not have foo.txt anymore in your working directory.

### Collaboration
You can add collaborators i.e., people that have write access (ability to push commits) to the repository to enable working in teams.

1) Head on over to your repository on GitHub. Navigate to the `Settings` section.
2) In the left section under `Access`, you'll find `Collaborators`.
3) Click `Add People` to add your team.

## Assignment 0
Head on over to the Assignment 0 URL shared with you in LMS. Be sure to log in using your GitHub account you are going to use for the rest of this course. Using that link, you can select your Qalam ID from the dropdown menu and accept this assignment. The assignment is intended to familiarize students with submissions over [GitHub Classroom](https://classroom.github.com/) platform. 

More details about the assignment will be available in its README.md file.

## Setting up Git Environment
Transform your terminal for Git.

![diff](https://user-images.githubusercontent.com/113828118/191312166-59dd6bd7-bddb-42d0-830f-96318a9cd8aa.svg)

### Softwares used
- [Windows Terminal](https://github.com/microsoft/terminal/) 
- [Powershell](https://github.com/PowerShell/PowerShell/) 
- [Windows Package Manager](https://github.com/microsoft/winget-cli)
- [Oh-My-Posh](https://github.com/JanDeDobbeleer/oh-my-posh/)
- [Powerline](https://github.com/powerline/powerline)
- [Posh-git](https://github.com/dahlbyk/posh-git) 
- [Visual Studio Code](https://github.com/microsoft/vscode)

### Procedure
0) Open up the `Start Menu` and type `PowerShell` to open up Windows PowerShell. PowerShell is a command-line shell that is a successor to the legacy `Command Prompt` (commonly known as cmd). 

> We will perform all software installations through the command line using Windows Package Manager. Normally, `Windows Package Manager (winget)` gets pre-installed with a Windows Update and most likely already available in your machine in `PowerShell`. 
Verify installation of winget through running the command inside PowerShell `winget -v`. If you see a version number, this indicates winget is intalled on your machine.

> If you don't find it installed, you can either download it from [Microsoft Store](https://apps.microsoft.com/store/detail/app-installer/9NBLGGH4NNS1) or through the [Windows Package Manager Repository](https://github.com/microsoft/winget-cli/releases) (Download `.msixbundle` file under `Assets` of the latest `stable` release).

1) Install `Windows Terminal` using Windows Package Manager (winget) by running the command in PowerShell:

```
winget install Microsoft.WindowsTerminal
```
> Accept source agreements if prompted by typing in `Y`.

2) Once installed, close PowerShell and open `Terminal` through **Start Menu** and install `Git` through the command:

```
winget install Git.Git --interactive
```
  - When asked to choose default editor for Git, the default option is `Use Vim (the ubiquitous text editor) as Git's default editor`. It is recommended to change this option to `Use Visual Studio Code as Git's default editor`. 
  > If you do not have VS Code installed, you can open up a new tab inside Terminal and run the command `winget install code` and continue with Git's installation once Visual Studio Code has been installed.
  - Recommended to leave other options to their default and continue with the installation.
  - If you already have Git installed in your machine and want to switch Git's default editor from Vim to VS Code, you can do so through the following command `git config --global core.editor "code -w"`. Verify that the editor has been switched through the command `git config --global -e`. The file should now open in VS Code.

3) Install `Oh My Posh` for allowing custom themes on the terminal.

```
winget install JanDeDobbeleer.OhMyPosh
```

4) Install `posh-git` for enabling Git related themes on the terminal.
```
PowerShellGet\Install-Module posh-git -Scope CurrentUser -Force
```

5) Close the current instance and launch terminal again in `administrator` mode (Right-click icon in Start Menu and select **Run as Administrator**). To allow running of custom scripts inside PowerShell, enter in the following command:

```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Unrestricted
```

6) To add startup configurations to the PowerShell instance running inside Terminal, we need to modify the configuration file for PowerShell. The configuration file is named `Microsoft.PowerShell_profile.ps1`.

The default location for the file is `C:\Users\<your-username>\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1` or more succintly `%USERPROFILE%\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1`. 

> The location may vary if you have OneDrive installed on your machine, so you can use the command `echo $PROFILE` to get the location of the configuration file. In any case, we are going to modify this file by opening it up in VS Code.

> Don't worry if you don't find the specified file in the directory. The below command will create this file for you if it doesn't exist. 

```
code $PROFILE
```

7) Add the following lines of code inside the configuration file
```
Import-Module posh-git
oh-my-posh init pwsh --config "$env:USERPROFILE\Documents\WindowsPowerShell\themes\oh-my-posh_theme.omp.json" | Invoke-Expression
```
  - The `$env:USERPROFILE` expands to your user folder location inside Windows. In most cases it exapnds to `C:\Users\<your-username>` inside which the WindowsPowerShell directory is located. In some cases, if you have `OneDrive` installed, the default user location may be different. In case of a different location, consider updating the path in the 2nd line to the location where your `WindowsPowerShell` directory is located that can be viewed by `echo $PROFILE`. 
  - Notice we refer to `WindowsPowerShell\themes` directory even though we have not created such a directory. This will be done in the next step.
  - Save the file (or enable autosave in VS Code by navigating to File tab in top-left corner and select Auto Save) and exit VS Code.

8) Create a new folder called `themes` inside WindowsPowerShell directory and add the following file inside the directory.
  [oh-my-posh_theme.omp.json](/files/themes/oh-my-posh_theme.omp.json)

9) Re-launch terminal. You may notice new symbols that are not being rendered properly. This is because to load these status symbols (otherwise known as [Powerline Glyphs](https://news.ycombinator.com/item?id=15255696), you need `Powerline` fonts). We're going to install a Powerline font [Caskaydia Cove Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/latest/download/CascadiaCode.zip).
  - Extract the zip archive to a folder.
  - Select all `.otf` font files excluding the `LICENSE` and `README.md` file inside the directory.
  - Right-click and select `Install`.

10) To make use of the newly installed Powerline font, press the shortcut key `Ctrl+Shift+P` inside Terminal, type `Settings` inside the command-line and select the option `Open settings file (JSON)` (not to be confused with `Open default settings file (JSON)`) and replace the contents of the opened settings.json file with [this file](/files/settings.json).

11) Re-launch the terminal. Voilà! You finally have an awesome looking terminal all set for using Git/GitHub. (Granted this was more tedious than it should've been). 

> You can test out the Git powerline symbols by opening the terminal in any local git repository. Moreover, you can learn more about what each of the symbols for Git mean on [posh-git documentation](https://github.com/dahlbyk/posh-git#git-status-summary-information).

## Contribution
Feel free to contribute to this lab as well if you believe something can be improved! The aim is to make an introductory Git/GitHub lab that is easily digestible for new students and exposes them various different ideas.

## Resources
- [Git/GitHub Beginner Tutorial](https://www.youtube.com/watch?v=8JJ101D3knE)
- [Write good commit messages](https://cbea.ms/git-commit/)
- [An example repository with good commit messages](https://github.com/chocolatey/choco/pulls?q=is%3Apr+is%3Aclosed)
- [Intermediate Git Tutorial - Learn Git Data Model](https://www.youtube.com/watch?v=2sjqTHE0zok)
