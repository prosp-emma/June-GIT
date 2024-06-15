#Steps to Ensure VS Code is Using the Correct Credentials:

Open VS Code Settings:
Go to File > Preferences > Settings or use Ctrl+,.
Search for Git:
Look for settings related to Git, such as Git: Terminal Authentication, and ensure it's enabled.

Clear Credential Cache (if needed):
      git credential-cache exit

 Push Changes to GitHub
After updating your credentials, you can push your changes to the new account:
     git push origin your-branch-name

#Authentication
1.Using SSH Keys:
Generate a New SSH Key (if you don't have one for the new account):

    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
 
Add the SSH Key to the SSH Agent:
eval "$(ssh-agent -s)"
     ssh-add ~/.ssh/your_new_key_name

Add the SSH Key to Your GitHub Account:
     cat ~/.ssh/your_new_key_name.pub
Go to GitHub and navigate to Settings > SSH and GPG keys > New SSH key. Paste the key and save it.

Update Your Repository to Use SSH:
    git remote set-url origin git@github.com:your-username/your-repo.git

2.Using Personal Access Tokens (PAT):
Generate a Personal Access Token:

Go to GitHub, navigate to Settings > Developer settings > Personal access tokens > Generate new token. 
Select the scopes you need (typically repo).
Copy the generated token.
Update Remote URL with the Token:

In your terminal, navigate to your repository and update the remote URL to include the token:

     git remote set-url origin https://<your-token>@github.com/your-username/your-repo.git


     # check crede
     git config --global -e
