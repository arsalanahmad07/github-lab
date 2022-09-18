# Git and GitHub

## Assignment 0
Head on over to the Assignment 0 URL shared with you in LMS. Be sure to log in using your GitHub account you are going to use for the rest of this course. Using that link, you can select your Qalam ID from the dropdown menu and accept this assignment. The assignment is intended to familiarize students with submissions over [GitHub Classroom](https://classroom.github.com/) platform. 

More details about the assignment will be available in its README.md file.

## Setting up Git Environment

### Softwares used
- [Windows Terminal](https://github.com/microsoft/terminal/) 
- [Powershell](https://github.com/PowerShell/PowerShell/) 
- [Windows Package Manager](https://github.com/microsoft/winget-cli)
- [Oh-My-Posh](https://github.com/JanDeDobbeleer/oh-my-posh/)
- [Powerline](https://github.com/powerline/powerline)
- [Posh-git](https://github.com/dahlbyk/posh-git) 
- [Visual Studio Code](https://github.com/microsoft/vscode)

### Procedure
Normally, `Windows Package Manager (winget)` gets pre-installed with a Windows Update and most likely already available in your machine in `PowerShell`. If not, you can either download it from [Microsoft Store](https://apps.microsoft.com/store/detail/app-installer/9NBLGGH4NNS1) or through the [Windows Package Manager Repository](https://github.com/microsoft/winget-cli/releases) (Download `.msixbundle` file under `Assets` of the latest `stable` release).

Verify installation of winget through running the command inside PowerShell `winget -v`.

1) Open up `PowerShell` and install `Windows Terminal` using `Windows Package Manager (winget)` through the command:

```
winget install Microsoft.WindowsTerminal
```
> Accept source agreements if prompted by typing in `Y`.

2) Once installed, close `PowerShell` and open `Terminal` through **Start Menu** and install `Git` through the command:

```
winget install Git.Git --interactive
```
  - When asked to choose default editor for Git, the default option is `Use Vim (the ubiquitous text editor) as Git's default editor`. It is recommended to change this option to `Use Visual Studio Code as Git's default editor`. If you do not have VS Code installed, you can open up a new tab inside Terminal and run the command `winget install code` and continue with Git's installation once Visual Studio Code has been installed.
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

5) Close the current instance and launch terminal again in `administrator` mode. To allow running of custom scripts inside PowerShell, enter in the following command:

```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Unrestricted
```

6) To add startup configurations to the PowerShell instance running inside Terminal, we need to modify the configuration file for PowerShell. The configuration file is named `Microsoft.PowerShell_profile.ps1` and the default location is `C:\Users\<your-username>\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1` or more succintly `%USERPROFILE%\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1`. The location may vary if you have OneDrive installed on your machine, so you can use the command `echo $PROFILE` to get the location of the configuration file. In any case, we are going to modify this file by opening it up in VSCode.

```
code $PROFILE
```

7) Add the following lines of code inside the configuration file
```
Import-Module posh-git
oh-my-posh init pwsh --config "$env:USERPROFILE\Documents\WindowsPowerShell\themes\oh-my-posh_theme.omp.json" | Invoke-Expression
```
  - The `$env:USERPROFILE` expands to your user folder location inside Windows. In most cases it exapnds to `C:\Users\<your-username>`. In some cases, if you have `OneDrive` installed, the default user location may be different. Consider updating the path in the 2nd line to the location where your `WindowsPowerShell` directory is located in case the user profile location is different. 
  - Notice we refer to `WindowsPowerShell\themes` directory even though we have not created such a directory. This will be done in the next step.
  - Save the file and exit VS Code.

8) Create a new folder called `themes` inside WindowsPowerShell directory and add the following file inside the directory.
  [oh-my-posh_theme.omp.json](/files/themes/oh-my-posh_theme.omp.json)

9) Re-launch terminal. You may notice new symbols that are not being rendered properly. This is because to load these status symbols (otherwise known as [Powerline Glyphs](https://news.ycombinator.com/item?id=15255696), you need `Powerline` fonts). We're going to install a Powerline font [Caskaydia Cove Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/latest/download/CascadiaCode.zip).
  - Extract the zip archive to a folder.
  - Select all `.otf` font files excluding the `LICENSE` and `README.md` file inside the directory.
  - Right-click and select `Install`.

10) To make use of the newly installed Powerline font, press the shortcut key `Ctrl+Shift+P`, enter `Settings` inside the command-line and select the option `Open settings file (JSON)` (not to be confused with `Open default settings file (JSON)`) and copy paste the content from [this file](/files/settings.json) inside the settings.json file.

11) Re-launch the terminal. Voila! You finally have an awesome looking terminal all set for using Git/GitHub. (Granted this was more tedious than it should've been)

You can learn more about what each of the symbols for Git mean on [posh-git documentation](https://github.com/dahlbyk/posh-git#git-status-summary-information)

## Resources
- [Git Beginner Tutorial](https://www.youtube.com/watch?v=8JJ101D3knE)
- [Write good commit messages](https://cbea.ms/git-commit/)
- [An example repository with good commit messages](https://github.com/chocolatey/choco/pulls?q=is%3Apr+is%3Aclosed)
- [Intermediate Git Tutorial - Learn Git Data Model](https://www.youtube.com/watch?v=2sjqTHE0zok)
