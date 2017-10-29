# References:

- https://angular.io/guide/quickstart#quickstart (Angular tutorial)
- https://gist.github.com/Chaser324/ce0505fbed06b947d962 (Pull Request Documentation)
- https://guides.github.com/activities/hello-world/ (Git workflow)
- https://github.com/angular/angular-cli (Angular CLI)

# MY SETUP:
I think we broke that repository (project) in git. This is what I did to restart:

Installed all required stuff as indicated in the quick-start page (https://angular.io/guide/quickstart#quickstart). 

> **NOTE**: I also installed visual studio code as that's the preferred editor at SEI

On my local (I use BASH that is installed with git) I created a project as indicated in the quick-start [`ng new angular-heroes`]. this sets up a new angular project using angular CLI (which is also the preferred method here at SEI). 

> **NOTE**: This creates the project AND a LOCAL git repository

I created a NEW repository on my git account [angular-heroes] 

I Added the remote URL of the newly created folder using [`git remote add origin URL`]

Here is the summary of the commands i executed:

	cd [desired root folder like /c/src/ or c:\src]
	ng new angular-heroes
	cd angular-heroes
	git remote add origin https://github.com/GerardoVilleda/angular-heroes.git
	git push -u origin master
	ng serve --open

> **NOTE**: Running `ng serve --open` opens your default browser (mine is Chrome) on http://localhost:4200. You should see the Angular logo and a couple links. Ctrl-C stops the running `ng serve` command.

MY SETUP Done!

# YOUR SETUP STARTS HERE

You received an invitation from github. Logon to your account and accept clicking the `Accept invitation` button. 
After you click `Accept invitation` you will be in **MY** repostitory. Click the `Fork` button (top-right) corner. This will create your own repository from the original. 

You can now clone your forked repository and start the application as follows:

> **NOTE**: The command `code .` will open the Visual Studio code editor which I assume you have installed already

	cd [desired root folder like /c/src/ or c:\src]
	git clone https://github.com/jordanforbes/angular-heroes
	cd angular-heroes
	code .
	npm install
	ng serve --open
	
When you see the application running press `Ctrl-C` to stop the `ng serve` command. 

You will follow the instructions on this page (https://gist.github.com/Chaser324/ce0505fbed06b947d962) to work on your fork. First, you will add `upstream` as a remote to point to MY repository. This is where we would keep the FINAL OFFICIAL version that would go to production (if this was a real app). 

	git remote add upstream https://github.com/GerardoVilleda/angular-heroes.git
	git remote -v
	
Your first "assignment" will be to familiarize with the code in the default application generated using the angular cli and complete the tasks starting here (https://angular.io/tutorial/toh-pt1#keep-the-app-transpiling-and-running). 

> **NOTE**: No setup needed as that was done already.

Each time you start work on an application feature you must create a branch to store that code. In this step you will work on the hero editor and therefore you will work on the `hero-editor` branch. 

	git checkout master
	git branch hero-editor
	git checkout hero-editor
	
Make the changes on this page (https://angular.io/tutorial/toh-pt1#keep-the-app-transpiling-and-running) and play around with the code. 
You will commit your changes in Visual Studio code using the git support tab (https://code.visualstudio.com/docs/editor/versioncontrol#_git-support). 
Usually you only need to press `Ctrl-Enter` to add and commit your changes. You could also use `git add` and `git commit` commands if needed.

> **NOTE**: Answer `Yes` or `Always` when prompted if you would like to automatically stage all your changes and commit directly. 

After you have completed and tested your changes you can push to your repository (and branch)

	git push

> **NOTE**: You will need to enter user and password and another push may be required if you get an error indicating no changes were made. 

	git push origin hero-editor
	
Navigate to your forked repository and verify that your changes are there. Remember that a branch was created! Select the `hero-editor` branch from the drop down. 

# Pull Request
when you complete a logical set of changes (a feature or a bug fix) you submit the code for review and approval using a `Pull Request`. 

Navigate to your repository and select the pull requests tab (https://github.com/jordanforbes/angular-heroes/pulls)

Click the `New pull request` button.

You will see a message indicating that there isn't anything to compare. This is true as the master branch of your fork is identical than my master branch. 

> **NOTE**: Select the `hero-editor` branch from the compare drop-down (the last one to the right). 

After you select the right branch you will see the changes you made and can click the `Create pull request` button. 
This will take you to a page where you enter two things: 

1. Comments for the reviewers. This should be used to help the reviewer know what the changes are about, how critical are they, are they ready to be deployed, etc. 
2. A list of reviewers for the changes. You will select my ID `GerardoVilleda` from the `Reviewers` link (a small cog to the right of the `Reviewers` word)

> **NOTE**: It is important that you see a green message at the top that reads: `Able to merge`. This indicates that your changes don't conflict with changes that other developer could have made. 

When the notes and reviewers are set, click the `Create pull request` button. 

> **NOTE**: At this moment you are done and it is the job of the reviewer to check your code and add comments as needed. This process could continue for some time. 

> **NOTE**: The owner of the master repository (in this case me) is usually responsible for merging the code into the master branch. However you could merge the code yourself **AFTER** the reviewer has approved the changes.

After the code has been merged, you will run the following commands to ensure your local copy has the ltest version in the master repository.

	git fetch upstream
	git checkout master
	git merge upstream/master
	
> **NOTE** At this point you are done with changes. The process will repeat starting with the creation of a new branch (you can reuse the branch if more work is needed).

# AngularHeroes

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.4.9.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
