
# Learning the basics 
 - https://youtu.be/uR6G2v_WsRA by David Mahler
 - the book https://git-scm.com/book/en/

# Setting up git for the first time

0. go to https://github.com/settings/emails and check the box __Keep my email addresses private__ and use the provided email address shown for step 7
1. install git
2. create folder name `repos` in my docs (windows) or home (linux)
3. edit git bash shortcut (windows)
4. edit target to just "C:\Program Files\Git\git-bash.exe"
5. edit start in to "C:\Users\username\repos"
6. using shortcut should open git bash into \repos folder
7. `git config --global user.email user@domain.com`
8. `git config --global user.name "yourusername"`
9. `git config --global init.defaultBranch main`
10. check your work with `git config --list`

# Creating a Platformio Microcontroller Project with GitHub

1. create a new platormio project in platformio within the "repos" directory
2. on github, create new repository with same project name (so the folders match)
3. on github, copy link to repository
4. in git bash, navigate to new project folder and ...
	- `git init`
	- `git remote add origin https://github.com/yourusername/new_project_name_goes_here.git`
5. edit .gitignore to the following
		.pio/
		.vscode/
		.vscode/.browse.c_cpp.db*
		.vscode/c_cpp_properties.json
		.vscode/launch.json
		.vscode/ipch
6. in git bash ...
	- `git add .`
	- `git commit -m"initial commit"`
	- `git push origin main` ... (or master)
7. check github that platformio and such files are now present
8. you should now be synced with main branch and be ready to edit, commit, push, pull, etc.

# Copy/Paste in BASH

  - copy = CTRL + Insert
  - paste = SHIFT + Insert

# Useful git commands

## check global settings
`git config --list`

	user.name=John Doe
	user.email=johndoe@example.com
	color.status=auto
	color.branch=auto
	color.interactive=auto
	color.diff=auto

## Add a file that your forgot to commit (use before push)

`git commit -m 'Initial commit'`

`git add forgotten_file`

`git commit --amend`

`git push origin main`

You end up with a single commit — the second commit replaces the results of the first.
		
## Unstage a staged file
`git reset HEAD filethatneedsunstaging.txt`
 
This will not undo the file that has changed, just unstages that file for the next commit.
		
## Update git
`git update-git-for-windows`

## move MAIN back several commits ...
`git checkout main`

`git reset --hard <commit_hash>`

`git push -f origin main`

You should see the commits after your desired commit disappear online.
    
## unstage file(s) without changing anything

`git reset .`

`git reset README.md`
    
## discard changes to a file(s)

`git checkout -- myfile.md`

myfile.md goes back to its original from the last pull

## tagging (after commit)

`git tag v1.4.1`

`git push origin --tags`
    
## deleting tag

`git tag -d v2.1.2`

`git push origin :refs/tags/v2.1.2`  ...  tag is deleted

`git tag v2.2.0`  ... replace with desired tag

`git push origin --tags`
	
## change default text editor for git (usually for commit messages)
from whatever Microsoft messed it up to ...
	
`git config --global core.editor 'nano'`
or
`git config --global core.editor "'C:\Program Files (x86)\Notepad++\notepad++.exe' -multiInst -notabbar -nosession -noPlugin"`
or
`git config --system core.editor "'C:\Program Files (x86)\Notepad++\notepad++.exe' -multiInst -notabbar -nosession -noPlugin"`  ...  must run git bash as admin

## keeping email private 

`git config --global user.email user@domain.com`

`git config --global user.name "yourusername"`

`git config --global init.defaultBranch main`

becomes ... 
	
	From 22e3b924670658dd40edc4152f1389efdb84a923 Mon Sep 17 00:00:00 2001
  From: yourusername <user@domain.com>
  Date: Mon, 22 Aug 2022 14:46:56 -0400

## check origin/main for changes

`git diff origin`

or

`git diff main`
    

## see pretty tree map of repo
`git log --all --decorate --oneline --graph`
    
## so your last commit (called commitZ) for some reason has no parent ...

- move HEAD to commitY (commit before parentless commitZ)
  
  - `git reset --hard commitY_hash`
  
  - `git push origin HEAD --force`

- look at changes

  - `git log --all --decorate --oneline --graph`

  - `git merge commitZ_hash`  ...  (use hash)

- look at changes

  - `git log --all --decorate --oneline --graph`

  - `git push origin main`

- now commitZ should be latest commit pointed to by HEAD and origin/main

- check results online
## Find Lost/Dangling Commits

- show commits ... `git fsck --lost-found`
- create a new branch ... `git branch <new-branch-name> <commit_hash>`

## Edit commit message before push

- to revise/edit/whatever a local commit message ... `git commit --amend`

## Stop a main|MERGING

- git merge --abort

## Compare two commits in a browser

 - https://github.com/username/repo_name/compare/abcd123..456efgh