# SSH Life Blog

## Repo Structure
**Master Branch**
The `master` branch is for published material only. Writing your blog post should NOT be done in this branch.

**Content Branch**
Use the `content` branch to write your blog post and use a tool like ghp-import to transfer the content material to the master branch.

## Setting Up with Pelican
Blog posts for SSH Life are published with Pelican and Github Pages. You'll first want to get a Python virtual environment setup. Install the required packages first:

```
sudo apt-get install python-setuptools
pip install virtualenv --user
```

Create and activate the virtual environment then install Pelican. ghp-import is a nice tool that the Makefile in Pelican utilizes to copy the blog content from your `content` to the `master `branch. Markdown will be needed if you plan to write your blog in Markdown.
```
python -m venv pelican
source pelican/bin/activate
pip install pelican ghp-import Markdown

```

Clone the SSH Life repo
```
https://github.com/ssh-life/sshlife.github.io.git
```

You can switch between `master` and `content` branches via `git checkout`.

## Writing a Post
Switch to the `content` branch with `git checkout content`. You can confirm you've switched with `git log`.

Posts will be under the content directory.

**TODO** -> Figure out directory hiearchy.


## Generating a Post
There are a couple of ways the blog can be generated. You can utilize Pelican commands or the Makefile. I recommend utilizing Makefile commands to reduce mistakes and it's just easier.

### Makefile
**make github**

This will generate the Pelican output and copy the output material into the `master` branch with ghp-import. 

**make serve**

This will generate your page and host the blog on a local server. The material you've currently written will be hosted on 127.0.0.1:8000.