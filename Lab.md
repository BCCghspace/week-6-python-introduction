# Getting started with Python

We're going to be using Python in a few different settings this semester:
* Juptyer Notebooks for quick prototyping / experimentation and reproducible examples in labs
* Scripts running on your computer
* Scripts running on a computer in the cloud

Getting a Python environment setup is notoriously hard and annoying.

There are many ways to install Python. It comes by default with most operating systems, but usually lags by a couple of years so it is out of date on features. Python distributions can also be built from source code, installed via a system package manager like `apt-get` or `homebrew`, run in Docker... It gets confusing fast and it's not uncommon to have multiple Python distributions installed on a computer and paths and dependencies get mixed up.

To try to keep everything standardized for this class, we'll use Anaconda's [`Miniconda`](https://docs.conda.io/en/latest/miniconda.html) Python distribution. Anaconda is a well-maintained (and loved) Python distribution with a robust package management framework. `Miniconda` is a slimmed-down installation that's nice and small. It allows for easy additions of additional packages.

Anaconda's framework lets you:
* Create environments tagged to a specific version of Python (e.g., 3.8)
* Create separate (sandboxed) environments so you don't have to worry about conflicts between projects
* Install Python packages at an environment level, not system level. It is not advisable to install Python packages at the system level (e.g., don't do `sudo pip install ...` outside of virtual environments).

We're going to install the following packages today:

```yaml
name: musa509week6
channels:
  - defaults
dependencies:
  - python=3.8
  - geopandas
  - pandas
  - rtree
  - psycopg2
  - sqlalchemy
  - seaborn
  - pip
  - jupyterlab
  - pip:
    - cartoframes
    - google-cloud-bigquery[pandas]
    - nb-black
```

## Getting Python / Miniconda Installed 

1. [Download the Miniconda distribution](https://docs.conda.io/en/latest/miniconda.html) for your operating system
2. Install Miniconda
3. Open your computer terminal
    * Mac
      - Use the native Terminal app
      - [iTerm2](https://www.iterm2.com/) which is what I like
    * Windows
      - [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab)
    * Linux - if you're using Linux you probably already know what you like
4. Run `conda --version` to check that everything installed correctly. You should get a response like `conda 4.8.5`

## Installing Python env for this class

We'll use different environments depending on the project we're working on.

For our class today, there's a file in the repo called [`environment.yml`](https://github.com/MUSA-509/week-6-python-introduction/blob/main/environment.yml). Let's take a look at it.

**Setting up the environment**

1. Do one of the following:
    * Clone this repo: `git clone https://github.com/MUSA-509/week-6-python-introduction.git`
    * Download a zip file of this repo [`https://github.com/MUSA-509/week-6-python-introduction/archive/main.zip`](https://github.com/MUSA-509/week-6-python-introduction/archive/main.zip)
2. With your terminal, change directory (`cd`) into the directory where the repository is located. For example, if it is on your desktop: `cd ~/Desktop/week-6-python-introduction`. Here the `~` means the home directory.
3. Create a new environment from the `environment.yml` file:
    * Run this command in your terminal: `conda env create -f environment.yml`
    * This should take a minute or two to run while it install all the packages (and their dependencies) into a new environment.
4. Check that the environment is listed: `conda env list`
5. Activate the environment. This means you enter the environment so you can use Python with the packages you installed.
    * Run this command: `conda activate musa509week6`

## Python REPL

Let's look at the `python` command.

## Running a Jupyter server to view Lab Notebook

One of the packages installed is `jupyterlab`, which gives you a Jupyter Notebook server when you run the following command:

```
jupyter lab
```

Note: this will only work if you activated your conda environment.


## Don't forget to deactivate the environment!

Run this command to deactivate the Python environment we created:

```
conda deactivate
```
