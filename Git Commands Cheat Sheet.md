Below is a quick cheat sheet for common Git commands: 

## Setting up SSH

1. **Generate an SSH Key Pair:** Open a terminal or command prompt and enter the following command to generate an SSH key pair:
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
 
Replace `"your_email@example.com"` with your actual email address. You can also choose a different file name if you want to save the key pair with a custom name.

2. **Adding the SSH Key to SSH Agent (Optional):** To make working with SSH keys more convenient, you can add the private key to the SSH agent. Run the following command to add your private key:
```
ssh-add ~/.ssh/id_rsa
```

3. **Adding the Public Key to GitHub:** Open the public key file (by default, `~/.ssh/id_rsa.pub`) in a text editor and copy its contents. 
```
gedit ~/.ssh/id_rsa.pub
```

Then, follow these steps in your GitHub account:
- Go to Settings > SSH and GPG keys.
- Click on "New SSH key" or "Add SSH key."
- Paste the copied key into the "Key" field and give it a descriptive title.
- Click "Add SSH key."

5. **Testing SSH Connection:** To test if the SSH key is set up correctly, run the following command:
```
ssh -T git@github.com
```

 You should see a message indicating that you've successfully authenticated.

5. **Configuring Git to Use SSH:** Finally, configure Git to use SSH for authentication:
```
git config --global user.name "Your Name" 
git config --global user.email "you@example.com" 
git config --global core.sshCommand "ssh -i <location of id_rsa>"
// eg. git config --global core.sshCommand "ssh -i ~/.ssh/id_rsa"

```

Replace `"Your Name"` and `"you@example.com"` with your actual name and email.


### Navigate to D and switch to D:
````
cd /d d:
````
for VIP:
```
cd Purdue\Senior 1st Semester\VIP\Project\Lateral Thinking Puzzle
```
### Initiallize git and set branch to main
````
git init 
git checkout -b main
// You can add more branches if needed
````

### Check status, such as info of branch and files
````
git status
````

### Add all files
````
git add .
````

### Commit files
````
git commit -m "MESSAGE"
````

### Sets the new remote
````
git remote add origin <REMOTE_URL>
````

### Verifies the new remote URL
````
git remote -v
````

### Pushes the changes in your local repository up to the remote repository you specified as the origin
````
git push origin main
````

### Pulls the changes
````
git pull origin main
````

### Pull strategy
##### - Rebase
**Advantages of Rebase:**
- Creates a clean, linear history.
- Makes it easier to understand the evolution of the code.
- Your changes are **"on top"** of your friend's changes, potentially leading to a smoother integration.
```
git pull origin main --rebase
```
##### - Fast foward
**Advantages of Fast-Forward Merge:**
- Preserves a simple, linear history when your branch is an ancestor of the target branch.
- Suitable for integrating changes from a shared branch like `main`.

**Considerations:**
- If both you and your friend have made significant changes to the same parts of the codebase, a fast-forward merge might not be suitable as it won't automatically handle conflicts.
- If you want to preserve a clear separation of your changes and your friend's changes, you might lean towards using rebase.
```
git pull origin main --ff-only
```
##### - hard pull
- This command forcefully moves your local branch to the same commit as the remote `main` branch. It discards any local commits and changes.
```
git fetch origin main 
git reset --hard origin/main
```


### Push Strategy
##### - force push changes
```
git push origin main -f
```
