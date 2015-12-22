I ran into the same situation, and want to leave my band-aid solution for others.

The real issue in my case, and what I believe was yours is that debian-keyring debian-archive-keyring was not fetched. So when you error out, your Debian Guest should be running and you should be able to ssh into the instance. That being the case SSH in and run the following as vagrant:

wget http://www.dotdeb.org/dotdeb.gpg
sudo apt-key add dotdeb.gpg
Then exit your ssh session as vagrant, and from the host OS fire off a simple vagrant reload --provision Now that the keys have been added manually, there shouldn't be an issue.
# vagrant_debian7_PHP5.6.16
