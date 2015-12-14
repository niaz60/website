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

---

## UPDATING THE WEBSITE

The site's formatting is controlled by templates and static pages that rely on various data files. The files are either [YAML](http://www.yaml.org/) or Markdown (previously linked), and can be editted in a text editor. Notepad (Windows) and TextEdit (Mac) should be able to handle these files, but certain characters, like double quotations (") may not be handled correctly. For Windows, Notepad++ may do the trick, but here are a list of several (free) text editors that cover a wide range of file types and are much easier to use for programming.

- [TextMate](http://macromates.com/download) : My personal favorite, but is only available for Mac. The 2.0 beta version is free to use. It is a production version, but carries the beta label simply do signal it's still being updated regularly.
- [Atom](https://atom.io/) : Created by GitHub. Has some nice features and is very customizable.
- [Brackets](http://brackets.io/) : Created by Adobe. I have no personal experience with it, but is supposed to be another good option.
- [Light Table](http://lighttable.com/) : A Kickstarter backed creation, built with the quility to rival other bigger-name editors.

The majority of those files are located within the '_data' folder. Each subfolder within it corresponds to the webpage that it affects.

### main

The files that alter the [home page](http://acmml.com/).

- about.yml : The text for the 'About Us' section.
- images.yml : Determines what images are part of the primary rotating images.
- news.yml : Dictates how many news article snippets are displayed on the home page.

### people

Each file (graduate.yml, postdoc.yml, principal-investigator.yml, undergrad.yml) is where the info for each person within the research group goes. If, for instance, there are no post-docs then the file will be blank and that section on the People page will not show up. The available sections of information that can be filled out for a person are detailed in the comments section at the top of each file.

### publications

The publications.yml file is just a list of the publications. Each one has an 'id' that is simply for linking to a research section (to be detailed below). The rest is hopefully self-explanatory, but keep in mind the DOI will automatically create the appropriate link when listed out on the publications page. As with any of these data files, if a section is left blank is simply will not appear on the page.

### research

The research.yml file is a list of research areas, with corresponding information. The image, or video, that is chosen will show up (the video will supercede the image if both are listed), along with a linked publication title (if given), a title, and a description. Formatting for the description portion is a little confusing, but as a rule keep in mind that indentations in YAML are very particular. Each is exactly two spaces, and for the research descriptions, each new paragraph must have a blank line in between that contains 2 spaces in it. The new paragraphs must also be indented to the level of the first (4 spaces in total). Any links supplied in this area should work correctly on the research page. (Click on the Markdown link under the JEKYLL section to learn more on syntax. The descriptions will be parsed as Markdown.)

Videos are denoted by their YouTube ID. For ease of playback, accessibility, and keeping your site up-to-date, using YouTube to host your videos will be easier than other options. When you upload the videos onto YouTube just make sure they aren't set to Private, or they won't be allowed to be embedded on the site. You can, however, mark them as Unlisted, which means you have to have the direct link to view the video.

---

### news

The News articles are held in a different location. Starting in the main 'website' folder find the 'news' folder that will contain a '_posts' folder. Within it will be the news articles. The naming convention must be upheld of the article will be ignored. The correct convention is 'YYYY-MM-DD-name-of-article.md'. Within the article there will be a top section enclosed in '---' lines. The layout and category lines should never be altered, but the rest should be unique to each post. When creating new news articles it is easist to duplicate an earlier article and then change the name and details, so don't forget to update each piece of information. The articles will be ordered in the folder and on the site in reverse-chronological order (newest to oldest).

These news articles are Markdown files, and follow that syntax. Again, that link is available near the top of the JEKYLL section, above.

---

### adding images

When adding images, make sure they go into the appropriate folder. It should be noted in each data file where the images for that section go, and the directory setup matches that of the data files to make this easier.

Under the 'static/img/' folder there should be a header.jpg image. This is the banner image. If you should ever wish to replace it, simply remove this file and name the new image header.jpg. The four other folders correspond to the area they relate to. In the people folder there will be a blank.jpg image. Leave this image in the folder. It will be displayed for a person who hasn't given you an image to show yet.

I recommend trying to keep the filesize of the images you upload as small as possible. Under or around 100KB is ideal. For this to happen, usually JPEG files are the way to go. PNG files are much larger, and TIFF aren't compressed at all. JPEG can be compressed on a sliding scale, or resized as appropriate in any photo editting software. Preview on Mac actually handles this quite well. If an image is several thousand pixels in size it should be resized. For any image on the site a width of 800 should be perfectly fine and allow you to limit the file size. I wouldn't suggest going any lower than 800 in width. The only exception to this would be the header.jpg cover photo. A width around 1500 would be more advisable here, with a height no less than half of the width.

Also keep in mind that cropping images may be necessary. The people photos in particular should be cropped so they show up well on the site.

---