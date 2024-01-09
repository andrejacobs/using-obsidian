# TODO: ROUGH FIRST PASS

Method 1: (new git, then obsidian as vault)

Create a new GitHub repository
	TODO: what options
	
Copy the HTTPS URL for the repo and store it in a note

Create a Fine-grained Personal Access Token
	TODO: screenshots
	Github account settings, left hand side bar, scroll down and select Developer Settings
	Select Fine-grained tokens from the Personal access tokens menu
	Generate new token
	Fill in the details, select an expiration time, select only the repositories the token should have access to.
	Permissions
		Give "Read and Write" permission to "Commit statuses" and "Contents"
		
	Copy the token and store it in a note. You will not be able to copy or see this value again.

The correct URL to use with the personal access token will look like this:
	https://TOKEN@github.com/USER-NAME/NEW-REPO.git
	Essential just paste the token between https:// and github.com and add @ to seperate the token from the domain.

Clone the repo to your local machine
	Open terminal
	cd ~/Documents
	git clone https://TOKEN@github.com/USER-NAME/NEW-REPO.git
		
Open Obsidian
In the menu bar choose File | Open vault ...
Select "Open folder as vault"
Navigate to where you cloned the git repo. Ensure you select the directory containing the repo (i.e. the directory containing the hidden .git directory and the README.md file)

NOTE: Plugins are installed per Obsidian Vault
Next install the Obsidian Git plugin.
Open the Settings (Cmd + ,). Select "Community Plugins" and "Turn on community plugins".
Browse and search for "git". Select "Obsidian Git" by Vinzent (Denis Olehov).
Install. You should see a message popup briefly stating it was successful.
Enable the plugin and restart Obsidian.

If you look in Finder you should see a hidden ".git" and ".obsidian" directories for the repository directory. (To see hidden files Cmd + Shift + .)

In Obsidian open the Command Palette (Cmd + p). and type "git control". Select "Obsidian Git: Open source control view".
Here you can see the git repo status and any changes that need to be committed etc.
You will notice that a bunch of files are shown and these are all the .obsidian vault files that still need to be committed to the git repo (and pushed to origin).
Select "backup". This will commit and push all changes to the git repo.

You can verify the commit and push worked by going to the GitHub repository. There should be a .obsidian directory as well as a commit message like "vault backup: ....."
