# E: Could not get lock /var/lib/dpkg/lock-frontend — open (11: Resource temporarily unavailable)
### If you were trying to run this command in the terminal:
    $ sudo apt install software-properties-common
### And this is the error message you may get:
#### E: Could not get lock /var/lib/dpkg/lock-frontend - open (11: Resource temporarily unavailable)
#### E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock frontend)
#### is another process using it?
### Here, below is what you need to do:
#### First, this may happen if
#### Synaptic Package Manager’ or ‘Software Updater’ is open.
#### Some apt command is running in Terminal.
#### Some apt process is running in background.
### For above wait for the process to complete. If this does not happen run in terminal:
    $ sudo killall apt apt-get
### If none of the above works, remove the lock files. Run in terminal:
    $ sudo rm /var/lib/apt/lists/lock
    $ sudo rm /var/cache/apt/archives/lock
    $ sudo rm /var/lib/dpkg/lock*
### then reconfigure the packages. Run in terminal:
    $ sudo dpkg --configure -a
    $ sudo apt update
### That should do the job.
