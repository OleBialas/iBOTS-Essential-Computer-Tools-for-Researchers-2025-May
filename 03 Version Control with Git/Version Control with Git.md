# Version Control with Git


In this unit, we will learn how to use Git to track changes, manage
collaboration, and maintain a history of modifications. Git helps
researchers keep versions of their work, making it easier to collaborate
and revert to previous states when needed. This unit covers essential
Git commands for tracking changes, committing updates, and reverting to
older versions. It also includes instructions on using Git within VS
Code for an easier workflow.

## Setting up Git

Before using Git, you need to install it on your system. Installation
methods vary depending on your operating system. Here are the links for
installation instructions on the official website.

#### macOS

[Installation instructions: macOS](https://git-scm.com/downloads/mac)

#### Linux

[Installation instructions: Linux](https://git-scm.com/downloads/linux)

#### Windows

[Installation instructions: Windows](https://git-scm.com/downloads/win)

#### Configuring Identity for Git

Before using Git on your system, the first step is to configure your Git
username and email address. This ensures that Git associates your
identity with every commit you make.

In the terminal, type

``` bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Tracking Changes

Git helps track changes in your project by monitoring file
modifications. You can check the status of your changes, add files to be
included in the temporary staging area, and unstage them if needed. This
section covers the basic commands for tracking changes and how to use
the VS Code interface for Git.

The temporary staging area holds changes before they are committed
(saved permanently in the repository’s history). You can stage modified
files, newly created files, and deleted files.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr>
<th>Command</th>
<th>Description</th>
<th>VS Code GUI</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>git init</code></td>
<td>Initialize a new Git repository in the current directory</td>
<td>Click <strong>Source Control (Ctrl + Shift + G)</strong> → Click
<strong>“Initialize Repository”</strong></td>
</tr>
<tr>
<td><code>git status</code></td>
<td>Show the status of changes in the working directory</td>
<td>Click <strong>Source Control (Ctrl + Shift + G)</strong> → See the
file changes</td>
</tr>
<tr>
<td><code>git add file1.txt</code></td>
<td>Stage <code>file1.txt</code> for commit</td>
<td>Click <strong>➕ (plus) icon</strong> next to the file in
<strong>Source Control</strong></td>
</tr>
<tr>
<td><code>git add .</code></td>
<td>Stage all modified and new files</td>
<td>Click <strong>➕ (plus) icon</strong> next to each file OR Click
<strong>“Stage All Changes”</strong></td>
</tr>
<tr>
<td><code>git reset file1.txt</code></td>
<td>Unstage <code>file1.txt</code></td>
<td>Click <strong>➖ (minus) icon</strong> next to the file to move it
back to “Changes”</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 1**</span> Create a new folder
for your Git repository and open this folder in a new VSCode window.

<span class="theorem-title">**Exercise 2**</span> Initialize a Git
repository in this folder.

<span class="theorem-title">**Exercise 3**</span> Check the status of
the repository using `git status`.

<span class="theorem-title">**Exercise 4**</span> Create a file called
`experiment_1.txt` and check the status of the repository. Then, stage
the file and check the status again.

<span class="theorem-title">**Exercise 5**</span> Create two files
called `experiment_2.txt` and `experiment_3.txt` and check the status of
the repository. Then, stage both files together and check the status
again.

<span class="theorem-title">**Exercise 6**</span> Unstage
`experiment_3.txt` and check the status.

<span class="theorem-title">**Exercise 7**</span> Delete
`experiment_3.txt` and check the status.

## Committing Changes and Viewing History

The staged changes are still only temporary. To create a more permanent
snapshot of your project, you need to save the staged changes using a
`commit`. A commit records a snapshot of your project at a particular
time described by a commit message. Essentially, your project will be a
series of commits and the changes committed can be accessed via the
commit history.

In Git, each commit has a unique **commit hash**, which is a long ID
that helps track changes. Commits are saved in order, creating a history
of changes in the project. You can see past commits using `git log`,
which shows the commit hash, message, and time of each commit. **A
typical workflow would be that you *stage* any change you make to the
files in the temporary staging area and once you are happy with the
changes you have made, you *commit* them**. The point where you
**stage** and **commit** are up to you. This section covers committing
changes, adding messages, and viewing commit history.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 37%" />
<col style="width: 37%" />
</colgroup>
<thead>
<tr>
<th>Command</th>
<th>Description</th>
<th>VS Code GUI</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>git add f1.txt f2.txt</code></td>
<td>Stage specific files for commit</td>
<td>Click <strong>➕ (plus) icon</strong> next to the files in
<strong>Source Control</strong></td>
</tr>
<tr>
<td><code>git commit -m "Commit message"</code></td>
<td>Commit staged files with a message</td>
<td>Click <strong>✔ (checkmark) icon</strong>, enter commit message, and
press Enter</td>
</tr>
<tr>
<td><code>git add .</code></td>
<td>Stage all modified and new files</td>
<td>Click <strong>➕ (plus) icon</strong> next to
<strong>Changes</strong></td>
</tr>
<tr>
<td><code>git commit -am "Commit message"</code></td>
<td>Stage and commit all modified files in one step</td>
<td>Click <strong>“Stage All Changes”</strong>, then <strong>✔
(checkmark) icon</strong></td>
</tr>
<tr>
<td><code>git log</code></td>
<td>View the full commit history of the repository</td>
<td><strong>N/A</strong> (Command-line only)</td>
</tr>
<tr>
<td><code>git log --oneline</code></td>
<td>View a compact version of the commit history</td>
<td><strong>N/A</strong> (Command-line only)</td>
</tr>
<tr>
<td><code>git log -2</code></td>
<td>Display the last two commits</td>
<td><strong>N/A</strong> (Command-line only)</td>
</tr>
<tr>
<td><code>git diff</code></td>
<td>Compare the working directory with the last commit</td>
<td>Click on the file in <strong>Source Control</strong> and check the
inline diff</td>
</tr>
<tr>
<td><code>git diff &lt;commit-hash1&gt; &lt;commit-hash2&gt;</code></td>
<td>Compare two specific commits</td>
<td><strong>N/A</strong> (Command-line only)</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 8**</span> Commit the staged
files `experiment_1.txt` and `experiment_2.txt` with a message “create
files”.

<span class="theorem-title">**Exercise 9**</span> Add some text to
`experiment_1.txt` and check the repository status. Then, stage the
changes and check the status again. Finally, commit the changes with a
message “add data to exp 1”.

<span class="theorem-title">**Exercise 10**</span> Modify the content of
`experiment_1.txt` and check the repository status. Then, stage and
commit the change with a suitable commit message.

<span class="theorem-title">**Exercise 11**</span> Add some text to
`experiment_2.txt`. Then, stage and commit the changes in one step.

<span class="theorem-title">**Exercise 12**</span> View the full commit
history of the repository.

<span class="theorem-title">**Exercise 13**</span> Check a compact
version of the commit history.

<span class="theorem-title">**Exercise 14**</span> Display the history
of the last two commits

<span class="theorem-title">**Exercise 15**</span> Compare the
differences between the most recent commit and the working directory.

<span class="theorem-title">**Exercise 16**</span> Compare two specific
commits.

## Reverting to Older Versions

Git allows you to go back to a previous version of your work if needed.
Git offers several ways to do this. In this section, you will use one
such method where you undo the changes made in a particular commit
without losing the commit history. This is where having descriptive
commit messages can be useful in identifying which version you want to
go back to. In this section, we cover reverting changes using Git’s
`revert` command.

<table>
<colgroup>
<col style="width: 31%" />
<col style="width: 55%" />
<col style="width: 13%" />
</colgroup>
<thead>
<tr>
<th>Command</th>
<th>Description</th>
<th>VS Code GUI</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>git revert HEAD</code></td>
<td>Creates a new commit that undoes the latest commit</td>
<td>N/A</td>
</tr>
<tr>
<td><code>git log --oneline</code></td>
<td>Shows commit history in a short format</td>
<td>N/A</td>
</tr>
<tr>
<td><code>git revert &lt;commit-hash&gt;</code></td>
<td>Creates a new commit that undoes only the specified commit</td>
<td>N/A</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 17**</span> Modify
`experiment_1.txt` again and commit the changes.

<span class="theorem-title">**Exercise 18**</span> Use
`git log --oneline` to view the commit history.

<span class="theorem-title">**Exercise 19**</span> Revert the latest
commit using `git revert HEAD`.

<span class="theorem-title">**Exercise 20**</span> Check the status and
commit history to confirm the revert.

## Bonus: Producing a Merge Conflict

If the same lines have been changed multiple times, it may be that a
commit can not be integrated in the Git history automatically. In this
case, Git will indentify a **merge conflict** and prompt you to resolve
it manually. In this section, we will try to provoke a merge conflict
using the `revert` command.

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 21**</span> Modify and commit
changes to `experiment_1.txt` a few times.

<span class="theorem-title">**Exercise 22**</span> Use
`git log --oneline` to identify a specific commit to undo.

<span class="theorem-title">**Exercise 23**</span> Use
`git revert <commit-hash>` to undo only that commit. Were you able to do
this smoothly? Or did you get any conflicts? If so, why?

<span class="theorem-title">**Exercise 24**</span> Check the commit
history again to verify the changes.
