# Working with Remote Repositories using GitHub


In this unit, we will learn how to connect a local Git repository to
GitHub, clone an existing repository to work locally, and fork
repositories to contribute to open-source projects or collaborate with
others. GitHub provides a platform for storing repositories online,
enabling version control, collaboration, and backup of your work. This
unit covers essential commands for working with remote repositories.

### Creating a GitHub Account

1.  Go to [GitHub Sign Up](https://github.com/signup).  
2.  Fill in the required details.  
3.  Verify your email and complete the account setup.

## Pushing a Local Repository to GitHub

Once you have a local repository, you can push it to GitHub to store it
online and collaborate with others. This section covers adding a remote
repository, pushing changes, and setting an upstream branch for future
updates.

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
<td><code>git remote add origin &lt;URL&gt;</code></td>
<td>Link the local repository to a remote GitHub repository</td>
<td>Click <strong>Source Control (Ctrl + Shift + G)</strong> → Click
<strong>Publish Repository</strong></td>
</tr>
<tr>
<td><code>git push -u origin main</code></td>
<td>Push local commits to the remote repository and set upstream</td>
<td>Click <strong>Source Control</strong> → Click <strong>…</strong> →
Click <strong>Push</strong></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 1**</span> Open a local git
repository (you can use the one from the previous notebook) in a new
VSCode window.

<span class="theorem-title">**Exercise 2**</span> Go to your GitHub page
and xreate a new **public** repository on GitHub. IMPORTANT: initialize
it **without** a REAME file - it should be **completely empty**. After
you create the repository, copy the URL.

<span class="theorem-title">**Exercise 3**</span> In your local
repository, add the remote URL using `git remote add origin <repo-url>`

<span class="theorem-title">**Exercise 4**</span> Push the local
repository to GitHub using `git push -u origin main`.

<span class="theorem-title">**Exercise 5**</span> Go to GitHub to verify
that your repository now contains the pushed content.

<span class="theorem-title">**Exercise 6**</span> Add a new text file
with some content and commit the changes in local repository.

<span class="theorem-title">**Exercise 7**</span> Push the new commit to
GitHub using `git push -u origin main`.

<span class="theorem-title">**Exercise 8**</span> Check GitHub to verify
that your repository now contains the new file.

<span class="theorem-title">**Exercise 9**</span> Add new lines to the
text file and commit the changes in local repository.

<span class="theorem-title">**Exercise 10**</span> Push the new commit
to GitHub

<span class="theorem-title">**Exercise 11**</span> Check GitHub to
confirm that the changes are reflected in the file.

## Cloning a GitHub Repository to a Local Machine

If a repository already exists on GitHub, you can clone it to your local
machine to work on it. This section covers cloning repositories and
pulling the latest changes from GitHub.

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
<td><code>git clone &lt;repo-url&gt;</code></td>
<td>Clone a GitHub repository to a local machine</td>
<td>Click <strong>Source Control (Ctrl + Shift + G)</strong> → Click
<strong>Clone Repository</strong></td>
</tr>
<tr>
<td><code>git pull origin main</code></td>
<td>Pull the latest changes from GitHub</td>
<td>Click <strong>Source Control</strong> → Click <strong>…</strong> →
Click <strong>Pull</strong></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 12**</span> Open a folder that is
**not a Git repository** in a new VSCode window.

<span class="theorem-title">**Exercise 13**</span> opy the URL of the
repository containing the materials for this workshop:
https://github.com/ibehave-ibots/iBOTS-Essential-Computer-Tools-for-Researchers-Workshop

<span class="theorem-title">**Exercise 14**</span> In the VS Code
terminal, run `git clone <repo-url>` or use VS Code GUI to clone the
repository.

<span class="theorem-title">**Exercise 15**</span> Open the cloned
folder in VS Code and check that all the files are present on your local
machine.

<span class="theorem-title">**Exercise 16**</span> Create a new public
repository on GitHub, **this time initializing it with a README** and
copy the URL.

<span class="theorem-title">**Exercise 17**</span> In the terminal, run
`git clone <repo-url>` or use VS Code GUI to clone the repository.

<span class="theorem-title">**Exercise 18**</span> Open the cloned
folder in VS Code and check that the README file exists.

<span class="theorem-title">**Exercise 19**</span> Make a change
directly on GitHub (edit the README file and commit).

<span class="theorem-title">**Exercise 20**</span> In the terminal, run
`git pull origin main` or use VS Code GUI.

<span class="theorem-title">**Exercise 21**</span> Verify that the
changes are now in your local copy.

<span class="theorem-title">**Exercise 22**</span> Bonus: In a new
VSCode window, clone a public repository from another member of your
group. Then, let them make a change to their repository and pull the
change to your local clone

## Forking a Repository on GitHub

Forking allows you to create a personal copy of someone else’s
repository. This is useful for contributing to open-source projects or
working on repositories you don’t have direct write access to. This
section covers forking a repository, cloning the fork, and keeping it
updated with the original repository.

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
<td><strong>(GitHub UI)</strong></td>
<td>Fork a repository on GitHub</td>
<td>Click <strong>Fork</strong> on the GitHub repository page</td>
</tr>
<tr>
<td><code>git clone &lt;your-fork-url&gt;</code></td>
<td>Clone your forked repository locally</td>
<td>Click <strong>Source Control (Ctrl + Shift + G)</strong> → Click
<strong>Clone Repository</strong></td>
</tr>
<tr>
<td><code>git remote add upstream &lt;original-repo-url&gt;</code></td>
<td>Link the original repository as an upstream remote</td>
<td>NA</td>
</tr>
<tr>
<td><code>git push origin main</code></td>
<td>Push the merged changes to your forked repository on GitHub</td>
<td>Click <strong>Source Control</strong> → Click <strong>…</strong> →
Click <strong>Push</strong></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 23**</span> Go to GitHub and fork
the repository containing the materials for this workshop:
https://github.com/ibehave-ibots/iBOTS-Essential-Computer-Tools-for-Researchers-Workshop
and copy the URL of your fork.

<span class="theorem-title">**Exercise 24**</span> In a new VSCode
window, clone your forked repository using `git clone <your-fork-url>`.

<span class="theorem-title">**Exercise 25**</span> Make a change to the
README (or any other file) and commit them.

<span class="theorem-title">**Exercise 26**</span> Push the changes to
your forked repository using `git push origin main` and verify that your
repository contains the changes

## Collaborating on GitHub

<span class="theorem-title">**Exercise 27**</span> Create a new **public
GitHub repository** with a README file containing your name.

<span class="theorem-title">**Exercise 28**</span> Fork the repository
frm **another** member of your group.

<span class="theorem-title">**Exercise 29**</span> Clone the forked
repository locally using `git clone <fork-url>`.

<span class="theorem-title">**Exercise 30**</span> Add a new file (e.g.,
`hello_your_name.txt`) and commit the changes.

<span class="theorem-title">**Exercise 31**</span> Push the changes to
the forked repository.

<span class="theorem-title">**Exercise 32**</span> Creates a **Pull
Request (PR)** to the original repository from your fork.

<span class="theorem-title">**Exercise 33**</span> If you received a PR,
review it and merge it into your repository
