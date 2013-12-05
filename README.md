fap
===

fap - *F*abric *a*lternative for *P*OSIX, a semi-sarcastic automation tool.


Installation
------------

Put `bin/fap` in `/usr/local/bin/` or anywhere in your PATH.


Usage
-----

Create a `fapfile.sh` file in your project's root.  Here is a minimal
template, assuming you have a `vagrant` host configured in your
ssh config and the project resides in `/vagrant/src/` (this is where
the fapfile resides on the host):

```sh
HOST="vagrant"
REMOTE="/vagrant/src"

setup() {
    cd $REMOTE
}
```

If REMOTE is a VirtualBox shared directory of your project
tree, you are already good.  It it is a remote SSH server,
use `fap -p <command>` to scp the file over to HOST's REMOTE
before executing the command.

Now execute `fap sh` anywhere in your project directory tree.
You should get a shell from your HOST.


Adding commands
---------------

Let's add a command to your `fabfile.sh`.  Here is an example:

```sh
hello() {
    echo "Hello world!"
}
```

Sync the fapfile with your remote and run `fap hello`.  That's it!

