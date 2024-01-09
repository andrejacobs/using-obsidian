## Method 1 - my preferred method

I prefer to first create and clone a new git repository (hosted by [GitHub](https://github.com/)) and then turn that directory (the repo) into an Obsidian vault.

**NOTE:** I am using this as an example of what I would recommend to people that are comfortable with git, GitHub and macOS. Personally I use SSH and signed commits (GPG) for all my git repos and not HTTPS (with our without personal access tokens) but that is out of scope for this guide.

1. Create a [new GitHub repository](https://github.com/new)
	   I like to add the initial README.md file since it means the repo will already have an initial commit as well as an `.md` file to use for Obsidian.
	   ![[Screenshot 2024-01-09 at 12.10.26.png]]
	   ![[Screenshot 2024-01-09 at 09.07.52.png]]
2. Copy the HTTPS URL for the repo and store it somewhere (note, text file etc.).   
	   ![[Screenshot 2024-01-09 at 09.09.22.png]]
3. Create a Fine-grained Personal Access Token. This step is not required if you have configured your GitHub access for your specific needs (e.g. using SSH).
	   A personal access token allows you to restrict access to your GitHub repositories to only allow access to certain apps. It also makes it easy to revoke a token and therefore access.
	   
	1. Go to your GitHub account settings.
		   ![[Screenshot 2024-01-09 at 09.12.45.png]]
	2. Scroll down the options and select "Developer Settings".
	3. Select "Fine-grained tokens" from the Personal access tokens menu and "Generate new token".
		  ![[Screenshot 2024-01-09 at 09.15.57.png]]
	4. Fill in the details, select an expiration time, select only the repositories the token should have access to.
		![[Screenshot 2024-01-09 at 09.20.48.png]]
	5. Give "Read and Write" permission to "Commit statuses" and "Contents".
		![[Screenshot 2024-01-09 at 09.21.51.png]]
	6. Copy the token and store it somewhere (note, text file etc.). You will not be able to copy or see this value again.
	7. The correct URL to use with the personal access token will look like this:
		   Essentially just paste the token between https:// and github.com and add @ to separate the token from the domain.
		```
		https://TOKEN@github.com/USER-NAME/NEW-REPO.git
		```
4. Clone the repo to your local machine.
	   For example: Open the terminal.
	```
	$ cd ~/Documents
	$ git clone https://TOKEN@github.com/USER-NAME/NEW-REPO.git
	
	# Or if you want a differently named directory
	$ git clone REPO-URL "New Name Of Vault"
	```
	![[Screenshot 2024-01-09 at 09.35.08.png]]
5. Open Obsidian and in the menu bar choose File | Open vault ...
	   ![[Screenshot 2024-01-09 at 09.36.26.png]]
6. Select "Open folder as vault".
	   ![[Screenshot 2024-01-09 at 09.37.49.png]]
7. Navigate to where you cloned the git repo. Ensure you select the directory containing the repo (i.e. the directory containing the hidden .git directory and the README.md file).
8. Install the Obsidian Git plugin. **NOTE:** Plugins are installed per Obsidian Vault.
	1. Open the Settings (Cmd + ,). Select "Community Plugins" and "Turn on community plugins".
		   ![[Screenshot 2024-01-09 at 09.42.00.png]]
	2. Browse and search for "git". Select "Obsidian Git" by Vinzent (Denis Olehov).
		   ![[Screenshot 2024-01-09 at 09.43.11.png]]
	3. Install. You should see a message popup briefly stating it was successful. Enable the plugin and restart Obsidian.
		   ![[Screenshot 2024-01-09 at 09.44.05.png]]
9. If you look in Finder you should see a hidden ".git" and ".obsidian" directories for the repository directory. (To see hidden files Cmd + Shift + .)
	   ![[Screenshot 2024-01-09 at 09.46.51.png]]
10. In Obsidian open the Command Palette (Cmd + p). and type "git control". Select "Obsidian Git: Open source control view".
	![[Screenshot 2024-01-09 at 09.49.44.png]]
	Here you can see the git repo status and any changes that need to be committed etc. You will notice that a bunch of files are shown and these are all the .obsidian vault files that still need to be committed to the git repo (and pushed to origin).
	![[Screenshot 2024-01-09 at 09.51.42.png]]
11. Select "Backup". This will commit and push all changes to the git repo.
    ![[Screenshot 2024-01-09 at 09.52.29.png]]
12. You can verify the commit and push worked by going to the GitHub repository. There should be a .obsidian directory as well as a commit message like "vault backup: ....."
    ![[Screenshot 2024-01-09 at 09.53.18.png]]

You can also change the settings for Obsidian Git to automatically commit and push on an interval. For now I prefer to manually commit any changes to my Obsidian vaults.
