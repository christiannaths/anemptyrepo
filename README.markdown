## Cloning

To clone this repository to your desktop, try running this from terminal:

    git clone git@github.com:christiannaths/anemptyrepo.git ~/Desktop/anemptyrepo

The command you are running is the "git clone" command, which accepts
at least one parameter: the URI to the remote location where the
repository is found. In this example it's on Github at <code>git@github.com:christiannaths/anemptyrepo.git</code>

The second (optional) parameter is the local directory in which
you want to store the repository. So in this case it's on your
desktop in a folder with named with the ID of the gist: <code>~/Desktop/anemptyrepo</code>

so it's broken up like this:

    [git clone] [URI] [/path/to/cone/repo/into]


You should be able to navigate to your desktop and see the folder which now
contains the repo. In terminal run <code>cd ~/Desktop/anemptyrepo</code>


## Branching

Most repo's you will clone will have at least a <code>master</code> branch.
Sometimes you may wish to work directly from this branch, but sometimes you
may also wish to create a new branch so you can safely experiment and then
merge your changes in later.

First, run this command from terminal to see what branches exist:

    git branch

This should show you a list of branches (likely only one at this point), with
an asterix next to the _active_ branch, like so:

    *master

Add a new branch with:

    git branch updates20111011


Here is what's happening, you're running the <code>git branch</code> command with
one parameter, the name of a new branch you'd like to create. This will
copy the entire repo _at it's current state_ and separate it from the master
branch. It's now a completely independent set of code, in the same repo!

So, it breaks down like this:

    git branch [new_branch_name]

I like to timestamp my branches, but you can name them whatever you want, just
steer clear of spaces or speacial characters.

### Checkout a Branch

Now you'll need to checkout (use, or switch to) your new branch. You can
do that with:

    git checkout updates20111011

Now if you run <code>git branch<code> (without any parameters) agian it should
show you something like this:

    master
    *updates20111011

Note the asterix indicating that you are working on the new branch and
not the master.

