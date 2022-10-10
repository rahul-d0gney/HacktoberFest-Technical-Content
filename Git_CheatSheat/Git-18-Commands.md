**Welcome to `Top-18 Command`!**

<div align="right" markdown="1">

*[Read this in other languages](README.md#translations)*

</div>

# How to check your Git configuration:
The command below returns a list of information about your git configuration including user name and email:
<pre><code>git config -l</code></pre>

# How to setup your Git user email:
This command lets you setup the user email address you'll use in your commits.
<pre><code>git config --global user.email "signups@fabiopacifici.com"</code></pre>

# How to cache your login credentials in Git:
You can store login credentials in the cache so you don't have to type them in each time. Just use this command:
<pre><code>git config --global credential.helper cache</code></pre>

# How to initialize a Git repo:
Everything starts from here. The first step is to initialize a new Git repo locally in your project root. You can do so with the command below:

<code><pre>git init</code></pre>

# How to add a file to the staging area in Git:
The command below will add a file to the staging area. Just replace filename_here with the name of the file you want to add to the staging area.

<code><pre>git add filename_here</code></pre>

# How to add all files in the staging area in Git
If you want to add all files in your project to the staging area, you can use a wildcard . and every file will be added for you.
<pre><code>git add .</code></pre>

# How to add only certain files to the staging area in Git
With the asterisk in the command below, you can add all files starting with 'fil' in the staging area.
<pre><code>git add fil*</code></pre>

# How to check a repository's status in Git:
This command will show the status of the current repository including staged, unstaged, and untracked files.
<pre><code>git status </code></pre>

# How to commit changes in the editor in Git:
This command will open a text editor in the terminal where you can write a full commit message.

A commit message is made up of a short summary of changes, an empty line, and a full description of the changes after it.

<pre><code>git commit</code></pre>

# How to commit changes with a message in Git:
You can add a commit message without opening the editor. This command lets you only specify a short summary for your commit message.

<pre><code>git commit -m "your commit message here" </code></pre>

# How to commit changes (and skip the staging area) in Git:
You can add and commit tracked files with a single command by using the -a and -m options.
<pre><code>git commit -a -m"your commit message here"</code></pre>

# How to see your commit history in Git:
This command shows the commit history for the current repository:
<pre><code>git log </code></pre>

# How to see your commit history including changes in Git:
This command shows the commit's history including all files and their changes:
<pre><code> git log -p </code></pre>

# How to rollback the last commit in Git:
git revert will create a new commit that is the opposite of everything in the given commit.
We can revert the latest commit by using the head alias like this:
<pre><code>git revert HEAD</code></pre>

# How to switch to a newly created branch in Git:
When you want to use a different or a newly created branch you can use this command:
<pre><code>git checkout branch_name
</code></pre>

# How to list branches in Git:
You can view all created branches using the git branch command. It will show a list of all branches and mark the current branch with an asterisk and highlight it in green.

<pre><code>git branch</code></pre>

# How to remove a remote branch in Git:
If you no longer need a remote branch you can remove it using the command below:

<pre><code>git push --delete origin branch_name_here</code></pr
