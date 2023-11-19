# Steps for Setting Up Workflow with Colab, Google Drive, and GitHub

This file explains a workflow for integrating Google Colab, Google Drive, and GitHub to facilitate collaborative development and version control. Follow the steps below to set up this workflow:

## Step 1: Generate GitHub Access Token
1. Login to GitHub
2. Access Account Settings
3. Navigate to Developer Settings
4. Generate Token (for more details on token follow the article below)
5. Copy Token: Once generated, GitHub will display your new access token. Copy this token immediately
7. Create a new repository without any readme file

## Step 2: Colab and Google Drive Integration

1. Open a new notebook in Google Colab (Use this notebook as a terminal to write git commands).
2. Mount Google Drive to access and store files across sessions.

```python
from google.colab import drive
drive.mount('/content/drive')
```
3. Navigate to the Project Directory

```python
%cd /content/drive/MyDrive/dir_name/
```
upload or move your main colab notebook via Google Drive to this Directory.

4. Initialize and Configure Git

```python
!git init
!git config --global user.email "email@example.com"
!git config --global user.name "username"
```
```python
git_token = "token_generated_in_step_1"
repository = "repository_created_in_step_1"
username = "github_username"

!git remote add orign https://{git_token}@github.com/{username}/{repository}.git

!git remote -v
```

5. Add, Commit and Push Changes
```python
!git add .
!git commit -m "Commit Message"
!git push -u origin master
```

## Other Useful Commands
1. Git Remove
```python
!git rm file_name
```
2. Git Pull
```python
!git pull
```
3. Git Status
```python
!git status
````

Go to this article [How to Use Google Colab with GitHub via Google Drive](https://medium.com/analytics-vidhya/how-to-use-google-colab-with-github-via-google-drive-68efb23a42d) for more information.

