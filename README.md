linux-configs
=============

My Arch Linux config files

First create SSH keys to git server:
https://help.github.com/articles/generating-ssh-keys

ssh-keygen -t rsa -C "your_email@example.com"
# Creates a new ssh key, using the provided email as a label

# start the ssh-agent in the background
eval "$(ssh-agent -s)"
# Agent pid 59566
ssh-add ~/.ssh/id_rsa

sudo apt-get install xclip
# Downloads and installs xclip. If you don't have `apt-get`, you might need to use another installer (like `yum`)

xclip -sel clip < ~/.ssh/id_rsa.pub
# Copies the contents of the id_rsa.pub file to your clipboard

Now that you have the key copied, it's time to add it into GitHub:

Account settings buttonIn the user bar in the top-right corner of any page, click Account settings.
SSH Keys menuClick SSH Keys in the left sidebar.
SSH Key buttonClick Add SSH key.
In the Title field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
The key fieldPaste your key into the "Key" field.
The Add key buttonClick Add key.
Confirm the action by entering your GitHub password

to create a repo:

cd ~/
git init
  git add .bashrc
  git add .vimrc
  git add &lt;any other config files you want to add&gt;
  git commit -m 'Initial commit'
  git remote add origin git@github.com:coderholic/config.git # Your URL will differ
  git push origin master
  
to pull down to newly loaded arch linux:

git init
  git pull git@github.com:coderholic/config.git
  git remote add origin git@github.com:coderholic/config.git

to commit changes:

git commit -a -m "Useful commit message goes here"
  git push origin master
  
and fianlly:

git pull origin master  # on any machine needing the updates
