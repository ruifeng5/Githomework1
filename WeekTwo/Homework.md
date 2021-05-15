


# Week Two
This assignment is going to give you practice with merge conflicts and using the feature-based branching workflow. You are encouraged to refer to the slides and lecture video for any guidance (please do this *before* coming to office hours). If you are stuck, we are here for you in office hours or you can post to the Piazza.

This assignment is broken into 3 parts:
1. Merge conflicts
2. Branching
3. Pull requests

## Merge Conflicts

### Force a merge conflict (this is to give you a conflict to practice resolving)
> Remember, merge conflicts will happen when 1) there is a **merge** operation happening and 2) there are *conflicting* changes in the same area in your files. 

> In this section, we will force a conflict by creating conflicting commits and doing git pull. Keeping what we said above in mind, this will cause a conflict because pull has a **merge** operation under the hood (git fetch + **git merge**).

> **Important Note:** Of course, `git pull` is not the only way you can get a conflict. For example, you can get a conflict by merging two conflicting branches, but resolving a conflict is the same regardless of how the conflict is caused.
* Steps:
	1. Via GitHub, change `Addition.py` so that the addition function returns the product of two numbers (it currently subtracts)
		* To do this, go to the repository on GitHub, go to the `Week 2` folder, open `Addition.py`, and click on the pencil in the top right-hand corner of the file viewer
		* We are only doing this to simulate your teammate, working on the same repository as you, pushing a change to remote.
		* Editing files via GitHub can be useful for quick, minor hotfixes to .md or .txt files for example, but should not be your method for pushing actual code to GitHub
			* We will expect you to code locally and interact with git using the command line in this class (and... on this homework)
		* **Important Side-note**: Make sure *not* to pull the new changes from remote to your local repository
        	* Once done editing, add a meaningful commit message, make sure "Commit directly to the **master** branch" is selected, and press "Commit Changes"
    2. *Locally*, edit `Addition.py` so that the addition function returns the quotient (it should currently subtract on your local repository)
    3. Commit your changes locally
    4. Pull from the remote repository
        * This *should* cause a merge conflict
### **Resolve the merge conflict**
1. Resolve the merge conflict
	* If you open `Addition.py` again, you should see some `<<<<`, `====`, and `>>>>` 
	* The `====` is used to symbolize the two conflicting parts of the code - one on each side
	* All you have to do to resolve the merge conflict is to delete the arrows and equal signs, then rearrange the code to however you want it to look - in this case, get rid of the version that returns `x / y` and keep the one that returns `x * y`.
2. Once you have resolved the merge conflict, make sure to commit your changes
3. Push to GitHub. It is important to get into the habit of pushing frequently, especially if you're working in a group so that the people you're working with will always have access to the most up to date version of the repo. Keep in mind that the more frequently you push/pull to/from the remote, the less likely a merge conflict is!

## Branching
* Task: Use branching and merging to make changes to `Addition.py`
* Steps:
    1. Pull new changes from origin
        * Make sure you always do this whenever you resume working on a project (it's good practice!)
        * Especially in a team, you never know what changes might've been made in your absence
    2. Create a new branch
        * To avoid pushing directly to the master branch, we will be using a new branch (Remember, this is what we do whenever we add a new feature/bugfix/documentation/refactor/etc)
        * In this case, you will be using this new branch to **fix** the `addition` function
        * Remember to create a descriptive branch name
    3. Edit `Addition.py` so that the addition function returns the sum of two numbers (it currently multiplies after your modifications in the merge conflict section)
    4. Commit your changes to your new branch
        * Remember to create a descriptive commit message
    5. Push to remote

## Pull Requests
* Task: Use branching to fix `Addition.py` once and for all, using a GitHub Pull Request (PR) to have your changes reviewed. 
> Pull requests are important when working in teams because it allows others on your team to review your code, and if you wrote unit tests and configured your repository correctly GitHub will even run them automatically to make sure your code works before you merge back into the master branch (CS126 goes into unit testing, so we won't here)
* Steps:
     1. On GitHub, create a Pull Request from your new branch from the last section. 
         * You may have recieved a prompt with a `Compare & pull request` button. If that is the case, click the button in the prompt to proceed
         	* If you did not recieve the prompt, then you will need to get there manually. Click the `Pull requests` tab from the repository and click `New pull request`
         * Change compare to your new branch
         * Click `Create pull request`
    2. Add your Project Manager as a reviewer
	    * Reviewers are important because they will look through your code for errors and provide valuable insights into how you should improve what you wrote *before* it gets merged into the master branch
	    * In CS196, PM's very lightly review code to make sure nothing is obviously broken, but since CS126 goes through the full code review process, we don't focus on it
        * Click `Reviewers` on the righthand side
        * Type in your PM's GitHub username
    3. Click `assign yourself` under Assignees
	    * This is important because if someone comments on your Pull Request or a reviewer asks for a change, you will be notified as an assignee
	    * This also helps PM's keep track of who submitted what when a sprint is over
