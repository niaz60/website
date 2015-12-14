# Advanced Computational Mechanics and Materials Laboratory

##### Mechanical Engineering Department, University of Rochester

#### Niaz Abdolrahim, Principal Investigator

---

## GITHUB

The [site](http://acmml.com) is hosted in a [repository](https://github.com/niaz60/website) on GitHub. This README file can be found at that location, with the proper formatting.

### Adding/Changing Users

In order for someone to be able to edit the site, they first need permission to access the GitHub repo. As the owner, to edit who has the ability to edit the repo, go to [https://github.com/niaz60/website/settings/collaboration](https://github.com/niaz60/website/settings/collaboration), enter your password, and then add the username of the person you want to be able to have access. (In addition to the direct link above, you can access this by selecting Settings when at your repository's main page, and then selecting the Collaborators tab.)

### Allowing Direct SSH Access

In order to push/pull from GiHub without entering in a password for each action, the user will need to add an SSH key to his or her computer. **Only do this on your personal computer, that only you have access to. Do not add link an SSH key on a public computer to your GitHub account.** The best instructions for doing this are available at [https://help.github.com/articles/generating-ssh-keys/](https://help.github.com/articles/generating-ssh-keys/), with tutorials for all major operating systems.

### Interacting with GitHub

The easiest way to interact with GitHub is via the command line. You can edit/create/delete files from the browser interface, but it is usually much less practical. Git is a versioning software, and GitHub allows multiple users to edit one 'repository' of code by hosting it online. Each user hosts a version of this 'repo' on their own computer, and they must pull down updates from this online repo to stay current. Similarly changes made must be pushed to the online repo after updates.

(It is assumed git is already included on your computer for these instructions. If running 'git' on the command line does not produce a valid response please to go [https://git-scm.com/](https://git-scm.com/).)

#### Initial Clone

When first downloading the repo onto you computer, open up a command line window (Terminal on a Mac). Navigate to the folder where you want to store the website files (keep in mind this will create a folder titled 'website' with the repo stored inside.) with the command

    $ cd /<path>/<to>/<desired>/<location>

Then use the command 

    $ git clone https://github.com/niaz60/website.git

This should download all the website files onto your computer and initialize it as a git repository, linked to the online GitHub repo.

**From this point onward, make sure you are within the 'website' folder, and not any other location (including subfolders) in your command line window when executing commands.**

#### Pull

Every time you interact with your repo, make sure you pull down any updates that may have been done by another user. Make sure you are inside the 'website' folder in your command line window, then run the command

    $ git pull

All the changes should be made, otherwise the output of 'Already up-to-date' will be displayed.

#### Add/Commit/Push

To push your changes from your computer to the main repo at GitHub, you have to take several steps. This process is known as 'Committing' changes. The first step is to add files to your commit with 

    $ git add .

You can also add files individually, but this looks over the entire directory for any files that have been altered, added, or deleted. Then you have to commit these changes. Commits require a message to be added to give some information on what purpose the changes being made are serving. Commit commands look like this

    $ git commit -m "Your message goes here"

Your changes are now committed and ready to be pushed to the online repo with

    $ git push

You should see an output giving brief info on what was changed, and that your changes were applied successfully.

---

## JEKYLL

The site is hosted on GitHub via [GitHub Pages](https://pages.github.com/). It runs off the static website creator [Jekyll](http://jekyllrb.com/). (These links will have more in-depth details on both Jekyll and GitHub Pages, if the following instructions are not enough. This page also has good information [https://help.github.com/articles/using-jekyll-with-pages/](https://help.github.com/articles/using-jekyll-with-pages/)) Jekyll uses [Liquid](https://docs.shopify.com/themes/liquid-documentation/basics) templates, and compiles a static website from various data (YAML & [Markdown](https://daringfireball.net/projects/markdown/basics)) files and templates/static pages.

Once you've pulled from GitHub, you then use Jekyll to update the static website files on your computer before pushing the changes back to GitHub.

### Installing Jekyll

First, you must install Jekyll. Jekyll is simply a Ruby gem, but the install process could differ depending on how much you've used Ruby, or the command line in general. The following instructions are for Mac, and were taken from the installation docs, [http://jekyllrb.com/docs/installation/](http://jekyllrb.com/docs/installation/), and the troubleshooting guide, [http://jekyllrb.com/docs/troubleshooting/](http://jekyllrb.com/docs/troubleshooting/). Please see these links if more information is necessary.

    $ gem install jekyll

If this works, that's great and you can skip the next few steps (down to the ---). Otherwise, try this command

    $ gem update --system

If this works try the first command again. If it fails, you'll need to install XCode, which is Apple's Command Line Tools manager

    $ xcode-select --install

Once XCode is installed it should allow you to install Jekyll with

    $ gem install jekyll

If you're on El Capitan, it may say you can't install in that location. If it doesn't let you then use this command instead

    $ gem install -n /usr/local/bin jekyll

Hopefully by this point jekyll is installed. Check the install, which should display a list of available commands, with

$ jekyll

### Using Jekyll

Once Jekyl is installed there are only two commands that you will need to use to update the website. **As a reminder, these commands MUST be run in the 'website' folder, and no subfolder within it. If they are run within a subfolder an additional '_site' folder, which contains the static website files, will be created, and Jekyll will be unable to update the site any further. GitHub Pages will also be unable to recognize which set of files to use when hosting the website.**

The first command will allow you to preview the changes youve made before pushing them to GitHub. It automatically updates the static site files whenever a file is altered within the 'website' folder.

    $ jekyll serve

This will start a local server, available in a browser at [localhost:4000](localhost:4000). This local server will continue to operate until Control-C is used in the command line window to stop the process. **Don't forget to stop the command with Control-C once you are done previewing the site.**

If you don't need to preview your changes, you can simply run

    $ jekyll b

which builds the site again, and replaces the new static site files in the '_site' folder.