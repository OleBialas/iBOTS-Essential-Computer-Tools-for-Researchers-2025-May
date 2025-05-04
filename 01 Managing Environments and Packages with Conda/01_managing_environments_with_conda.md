# Managing Environments with Conda


In this unit, we will learn how to use Conda to manage packages and
environments. Conda allows us to create isolated environments to install
packages and manage research projects. We’ll start by installing our
editor VSCode and Conda.

### Installing Visual Studio Code (VSCode)

Simply follow [this link](https://code.visualstudio.com/download) to
download and install VSCode for your operating system

### Installing Conda via Miniforge

Miniforge provides a streamlined approach to Conda installation with a
minimal environment and access to the conda-forge community repository,
which is popular for its extensive collection of data science and
scientific computing packages. Miniforge is available for all major
operating systems, making it a flexible choice for cross-platform
development. **If you do not already have Conda installed** please
follow the instructions below to install Miniforge.

#### macOS & Linux

1.  Download the Miniforge installer for your platform from [Miniforge
    releases](https://github.com/conda-forge/miniforge/releases).

2.  Open a terminal and navigate to the download location.

3.  Run the installer:

    ``` bash
    bash Miniforge3-Linux-x86_64.sh  # or the macOS equivalent
    ```

4.  Follow the prompts to complete installation.

#### Windows

1.  Download the Miniforge installer for Windows from [Miniforge
    releases](https://github.com/conda-forge/miniforge/releases).
2.  Open and proceed through the installer with the default settings.
3.  To verify your installation, open the program `Minforge Prompt` and
    print the version of your Conda installation by typing:

``` bash
conda --version
```

## Creating and Managing Environments

One of the key advantages of Conda is its ability to create isolated
environments, which are essentially self-contained workspaces with their
own packages and dependencies. This allows us to experiment, develop,
and analyze data without worrying about conflicts between different
package versions, which can often disrupt workflows. This is especially
helpful for reproducible research: by keeping dependencies organized, we
ensure that our projects are replicable across systems.

This section covers the basics of creating, inspecting, activating, and
deactivating Conda environments.

<table>
<colgroup>
<col style="width: 39%" />
<col style="width: 60%" />
</colgroup>
<thead>
<tr>
<th>Command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>conda create -n env_name</code></td>
<td>Create a new environment named <code>env_name</code></td>
</tr>
<tr>
<td><code>conda create -p dir_name</code></td>
<td>Create a new environment in the specified directory
<code>dir_name</code></td>
</tr>
<tr>
<td><code>conda env list</code></td>
<td>List all existing Conda environments</td>
</tr>
<tr>
<td><code>conda activate env_name</code></td>
<td>Activate the environment <code>env_name</code></td>
</tr>
<tr>
<td><code>conda deactivate</code></td>
<td>Deactivate the current Conda environment</td>
</tr>
<tr>
<td><code>conda info --envs</code></td>
<td>Show paths and basic info about all environments</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 1**</span> Create a new empty
Conda environment named `test_env`.

<span class="theorem-title">**Exercise 2**</span> List all environments
to verify that `test_env` was created.

<span class="theorem-title">**Exercise 3**</span> Activate `test_env`
and confirm activation.

<span class="theorem-title">**Exercise 4**</span> Deactivate the
environment

## Managing Packages with Conda

Conda environment allow us to install libraries and dependencies
specific to each project. This helps avoid the challenges of “dependency
hell” where incompatible package versions interfere with each other.
Conda also allows us to install non-Python packagesm providing great
flexibility and power, especially for complex data workflows involving
multiple languages.

Per default, Miniforge’s distribution of conda will install packages
from the `conda-forge` channel which contains a wealth of scientific
packages for download - you can find the full list
[here](https://conda-forge.org/packages/)

<table>
<colgroup>
<col style="width: 44%" />
<col style="width: 55%" />
</colgroup>
<thead>
<tr>
<th>Command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>conda install package_name</code></td>
<td>Install <code>package_name</code> into the active environment</td>
</tr>
<tr>
<td><code>conda install package_name -y</code></td>
<td>Install <code>package_name</code> and automatically answer “yes”
when being asked for confirmation</td>
</tr>
<tr>
<td><code>conda install -c conda-forge package_name</code></td>
<td>Install <code>package_name</code> from the <code>conda-forge</code>
channel into the active environment.</td>
</tr>
<tr>
<td><code>conda list</code></td>
<td>List all installed packages in the active environment</td>
</tr>
<tr>
<td><code>conda remove package_name</code></td>
<td>Remove <code>package_name</code> from the active environment</td>
</tr>
<tr>
<td><code>conda clean --all</code></td>
<td>Remove orphaned packages to clean up the active environment</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 5**</span> Create and activate
new environment named `py_env`.

<span class="theorem-title">**Exercise 6**</span> Install `python=3.9`
in `py_env`.

<span class="theorem-title">**Exercise 7**</span> List all installed
packages and verify that you see Python with version 3.9.xx installed.

<span class="theorem-title">**Exercise 8**</span> Alternatively, type
`python --version` to verify Python was installed.

<span class="theorem-title">**Exercise 9**</span> Install the package
`numpy` into `py_env` and use the `-y` flag to automaticallt confirm the
installation. List all packages in `py_env` to confirm the installation

<span class="theorem-title">**Exercise 10**</span> Now use
`conda remove` to uninstall `numpy` and `list` all packages to confirm
numpy was removed.

<span class="theorem-title">**Exercise 11**</span> Even though
`conda remove`, removes a package (and it’s oprhaned dependencies) from
the environment, it won’t remove them from your computer - use
`conda clean --all` to clean up packages and files that are no longer
needed.

<span class="theorem-title">**Exercise 12**</span> Deactivate the
environment `py_env`

<span class="theorem-title">**Exercise 13**</span> Create and activate a
new environment called `r_env`. Then, install `r-base` and verify the
installation.

## Installing Packages with Pip

While conda provides its own package manager, the conda-forge repository
may not contain the package we are looking for. In this case, we can use
the package manager `pip` which allows us to install from the Python
Package Index (PyPI). PyPI is the largest repository for Python packages
and it is less curated than conda-forge, meaning that anyone can upload
their software there. By installing `pip` in our conda environment, we
can access packages in both repositories!

Please note that combining two package managers, `pip` and `conda`
within the same environment can lead to conflicts if they manage
dependencies differently. Thus, it is a good pratice to stick mostly to
`conda` and only use `pip` if needed.

<table>
<colgroup>
<col style="width: 44%" />
<col style="width: 55%" />
</colgroup>
<thead>
<tr>
<th>Command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>conda search something</code></td>
<td>Search the conda repositories for a package called
<code>something</code></td>
</tr>
<tr>
<td><code>pip install mypackage</code></td>
<td>Install <code>mypackage</code> into the current environment</td>
</tr>
<tr>
<td><code>pip uninstall mypackage</code></td>
<td>Install the <code>mypackage</code></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 14**</span> Activate the
environment `py_env`

<span class="theorem-title">**Exercise 15**</span> Seach the conda
repository for the `matplotlib` package, what does the printed message
say?

<span class="theorem-title">**Exercise 16**</span> Use `conda install`
to install `matplotlib`.

<span class="theorem-title">**Exercise 17**</span> Now, try to install
matplotlib using `pip install`, what does the printed message say?

<span class="theorem-title">**Exercise 18**</span> Now, install the
`slab` (soundlab) package. First, use `conda search` to see whether the
package is available via conda and, if not, install it via `pip`.

<span class="theorem-title">**Exercise 19**</span> Uninstall `slab`
again.

## Exporting and Importing Environments

Often, we would like to reproduce an environment across multiple
computers and potentially share it with our collaborators. With Conda,
we can `export` an evironment, which creates a file that lists all of
the packages that are installed with their exact version. With this
file, we can create an exact replication of the environment, even after
we deleted it or moved to a different setup.

<table>
<colgroup>
<col style="width: 43%" />
<col style="width: 56%" />
</colgroup>
<thead>
<tr>
<th>Command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>conda env export &gt; environment.yml</code></td>
<td>Save active environment configuration to
<code>environment.yml</code></td>
</tr>
<tr>
<td><code>conda remove -n env_name --all</code></td>
<td>Remove the environment <code>env_name</code> completely</td>
</tr>
<tr>
<td><code>conda env create -f environment.yml</code></td>
<td>Create a new environment from the file
<code>environment.yml</code></td>
</tr>
<tr>
<td><code>conda env list</code></td>
<td>List all conda environments</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

<span class="theorem-title">**Exercise 20**</span> Activate the `py_env`
environment and export it to a file named `py_env.yml`.

<span class="theorem-title">**Exercise 21**</span> Open `py_env.yml` in
VSCode by clicking it in the file browser on the left and quickly scan
its contents.

<span class="theorem-title">**Exercise 22**</span> Deactivate and remove
`py_env` using `conda remove -n py_env --all`. List all the environments
to verify that it has been removed.

<span class="theorem-title">**Exercise 23**</span> Recreate `py_env`
from the `py_env.yml` file.

<span class="theorem-title">**Exercise 24**</span> Verify the recreation
by activating `py_env` and listing the installed packages.

<span class="theorem-title">**Exercise 25**</span> Bonus: remove all the
environments you don’t want to keep after this session.
