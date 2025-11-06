Lab 01: Set up a Git repository with separate branches for frontend and backend, then merge them into the main branch
Objective

The objective of this lab is to create and manage a Git repository with multiple branches for different parts of a project — specifically a frontend and a backend branch.
The lab demonstrates:
How to initialize a Git repository
Create and switch between branches
Add and commit changes to different branches
Merge branches back into the main branch
Push all branches and final merged code to GitHub
Tools / Technologies
Git — Version control system to manage project history.
GitHub — Remote repository hosting platform.
Visual Studio Code or Terminal / Command Prompt — To run Git commands.
Docker Desktop — For later labs (not needed here).

Prerequisites
Before starting this lab, ensure the following:
Installed Software:
Git (check with git --version)
Visual Studio Code (or any terminal)
Configured Accounts:
A GitHub account to create a remote repository
Basic Understanding:
Git workflow: init, add, commit, branch, merge, push

Steps / Commands
1. Create a new project folder
mkdir lab01-git-repo
cd lab01-git-repo
This creates a working directory for the project.
2. Initialize a Git repository
git init
Creates an empty Git repository inside the folder.
3. Create an initial file and commit
echo "# My Fullstack Project" > README.md
git add README.md
git commit -m "Initial commit with README"
This adds and commits your first file to the main branch.
4. Create a new branch for the frontend
git branch frontend
git checkout frontend
You are now on the frontend branch.
5. Add frontend files
mkdir frontend
echo "<h1>Frontend Running</h1>" > frontend/index.html
git add .
git commit -m "Add frontend code"
This simulates your frontend development work.
6. Create a backend branch
Switch back to main first, then create the backend branch:
git checkout main
git branch backend
git checkout backend
7. Add backend files
mkdir backend
echo "console.log('Backend Running');" > backend/server.js
git add .
git commit -m "Add backend code"
Now you’ve developed backend files separately on their branch.
8. Merge frontend branch into main
git checkout main
git merge frontend
If Git says “Fast-forward,” it means the merge was automatic.
9. Merge backend branch into main
git merge backend
Now both frontend and backend code are merged into the main branch.
10. Verify final structure
ls

Expected structure:
backend/
frontend/
README.md

11. Create a GitHub repository
Go to https://github.com
Click New Repository →
Name it: lab01-git-repo
Keep it public, and do not initialize with README (you already have one).
Then copy the given remote URL.
12. Link local repo to GitHub and push
git remote add origin https://github.com/abhinay-078/lab01-git-repo.git
git branch -M main
git push -u origin main
Your local code is now on GitHub.
13. Push other branches (optional but recommended)
git push origin frontend
git push origin backend
You can now see three branches on GitHub:
main
frontend
backend
Expected Output / Result
Expected Git Commands Output:
git branch
  backend
* main
  frontend
git log --oneline --graph
*   Merge branch 'backend'
|\
| * Add backend code
* | Merge branch 'frontend'
|/
* Add frontend code
* Initial commit with README

Expected Folder Structure (after merging):
lab01-git-repo/
 ├── backend/
 │   └── server.js
 ├── frontend/
 │   └── index.html
 └── README.md
 Expected GitHub View:
Repository: lab01-git-repo
3 branches: main, frontend, backend
Merged content visible in main
Deliverables (What to Push)
Push the following to GitHub:
Labs/Lab01_Setup_GitRepo_BranchMerge.md   
Lab01_files/
 ├── screenshots/
 │   ├── git_branch_output.png
 │   ├── git_merge_log.png
 │   └── github_repo_view.png
 └── README.md
Always commit changes before switching branches.
Use git status frequently to check your branch and file states.
If merge conflicts occur:
Git will mark conflicts in files.
Open them in VS Code → fix conflicts → run:
git add .
git commit -m "Resolve merge conflicts"
Push all branches for visibility and grading.
