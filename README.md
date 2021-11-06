# sshlife blog

## Repo Structure
**Master Branch**
The `master` branch is for published material only. Writing your blog post should NOT be done in this branch and nothing should be modified manually in this branch.

**Content Branch**
Use the `content` branch to write your blog post. Running 'make github" will publish your article by copying the generated html to the master repo.

## Setting Up Pelican
Blog posts for SSH Life are published with Pelican and Github Pages. You'll first want to get a Python virtual environment setup. Install the required packages first:

```
sudo apt-get install python-setuptools
pip install virtualenv --user
```

Create and activate the virtual environment then install Pelican. ghp-import is a nice tool that the Makefile in Pelican utilizes to copy the blog content from your `content` to the `master `branch. Markdown will be needed if you plan to write your blog in Markdown. Double check what version of Pelican pip decides to install, it could be a very old version and you might need to install it by retrieving the source.
```
python -m venv pelican
source pelican/bin/activate
pip install pelican ghp-import Markdown

```

Clone the SSH Life repo
```
https://github.com/ssh-life/sshlife.github.io.git
```

You can switch between `master` and `content` branches via `git checkout`. The default should be 'content' and no manual changes should be performed on the master.

## Writing a Post
Switch to the `content` branch with `git checkout content`(this should be the default branch). You can confirm you've switched with `git status`.
Posts will be under the content directory. For any other pages, like about, contact us, etc. they should be under 'pages'.

### Directory Structure ###
Pelican utilizes the names of directories to populate the menu on the home page. Anything under the pages directory will be a static website and Pelican will utilize the metadata in the Markdown file to populate the menu. In the example below, "secureboot" will be displayed in the main menu and the following articles will be displayed. "pages" will *not* be displayed but the title metadata in about.md will be displayed.

sshlife.github.io/

├── content

│   ├── secureboot/

│   │   └── article1.md

│   └── pages

│   |   └── about.md


### Creating a New Category ###
A new category will be displayed on the home page menu. No requirement to make a new category but does make it nice if you're going to work on a series of posts. To make a new catgeory, simply create a new directory under the 'content' directory and add your article under the new directory.


## Generating a Post
There are a couple of ways the blog can be generated. You can utilize Pelican commands or the Makefile. Recommend utilizing Makefile commands to reduce mistakes and it's just easier.

**make devserver**
A convenient way to auto generate and display your changes on the web browser is with this command. It will not run in the background and recommend running this in a separate tab/terminal. 

**make serve**

This will generate your page and host the blog on a local server. The material you've currently written will be hosted on 127.0.0.1:8000.

## Publishing your Post

**make github**

This will generate the Pelican output and copy the output material into the `master` branch with ghp-import. Don't forget to commit and push your changes into the content branch. 


