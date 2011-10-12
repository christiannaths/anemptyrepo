## Cloning

To clone this repository to your desktop, try running this from terminal:

    git clone git@github.com:christiannaths/anemptyrepo.git ~/Desktop/anemptyrepo

The command you are running is the "git clone" command, which accepts
at least one parameter: the URI to the remote location where the
repository is found. In this example it's on Github at <code>git@github.com:christiannaths/anemptyrepo.git</code>

The second (optional) parameter is the local directory in which
you want to store the repository. So in this case it's on your
desktop in a folder with named with the name of this repo: <code>~/Desktop/anemptyrepo</code>

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

Now if you run <code>git branch</code> (without any parameters) agian it should
show you something like this:

    master
    *updates20111011

Note the asterix indicating that you are working on the new branch and
not the master.

## Making Changes

Now that you've swtiched to your new branch, you're free to make changes
to the code. Open the repo up in a text editor. If you are using
Sublime Text you can open it up from the command line with:

    cd ~/Desktop/anemptyrepo
    subl -n .

The first command navigates to the directory files for the current
branch of the repo are stored, and the second command opens the directory
in a new Sublime Text window (that's what the <code>-n</code> flag does).
Make a note of the <code> . </code> in that second line, that's telling
the <code>subl</code> command which directory to open, the <code> . </code> means "the current directory"


Now edit your code how ever you see fit. Add files if you need to. Try adding
a new file and call it whatever you like. Put something in it as a placeholder text.

After you've done that, type this into terminal:

    git status

This will list all of the files which have changed on your current branch.
You should see that new file you created in that list, something like:

    # Untracked files:
    #   (use "git add <file>..." to include in what will be committed)
    #
    # a_new_file.txt
    nothing added to commit but untracked files present (use "git add" to track)

The next step is to add these changed files to something called a "staging area"

## Committing Changes

Once you've made some changes to the code in the repo, you need to first
_stage_ these changes and then _commit_ them. To stage them, use the
<code>git add</code> command like so:

    git add .

This will add _all_ of the changed files to the staging area (that's) what
the <code> . </code> does. If you only wanted to add some of the changed
files you could type the name of the file instead of using the <code> . </code>

Now if you run <code>git status</code> again, it will show you the files
that have changed, along with which of those are _staged_ (ready to be committed).

Once you have the files staged that you want, commit them with:

    git commit -m "My most recent changes"

Here is what's happening. You're running the <code>git commit</code> and passing
it one parameter and one flag (or switch). The flag is <code>-m</code> and it tells
the command that you want to also provide a message to the commit (known as the
commit message). Then you're typing out your commit message in quotes. It's a good
idea to provide detailed commit messages so that when someone else works on
this project, they have a good idea of what you changed with each commit just
by looking at your message.

## Pushing Your Branch

Now you're ready to push your changes, safely contained within your branch, up
to the remote repo. Do that with:

    git push origin updates20111011

So here's the deal with this one: you're running the <code>git push</code> command
and passing it two parameters. The first is the _name_ of the remote reference (which
is essentially a convenient shortcut name that points to the URI of the remote repo, yup
that's the same URI that you used to clone the repo in the first place). And the second
is the name of your branch. So it breaks down like this:

    git push [remote alias name] [branch name]


Now you should be able to head over to the remote repo on Github (where you are now) and
see your changes under the new branch. You can navigate to the new branch by clicking on the
"Swtich Branches" button under the "Source" button from the repo's main navigation
on it's Github home page.
