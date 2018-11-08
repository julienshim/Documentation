# Create a Python 3 Development Environment and Install Django 3 on Python (Draft)

### Prerequisites

- macOS with administrative access
- internet connection

### Step 1 - Install Xcode

Check if you have Xcode from your `Applications` folder or running the following command from the `Terminal` app.

```
$ xcode-select -p
```

If you receive the following output, then Xcode is installed.

```
/Library/Developer/CommandLineTools
```

If you receive an error, then install Xcode from the App Store, then updated to install Xcode's separate Command Line Tools app, which you can do alternative by typing the following:

```
$ xcode-select --install
```

### Step 2 - Installing and Setting Up Homebrew

Visit the Hombrew website at (brew.sh/)[https://brew.sh/], and copy the provided link to your terminal. It should look like as follows:

```
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Step 3 - Inserting the Homebrew directory at the top of your PATH enviroment variable

Once you installed Homebrew, insert the Homebrew directory at the top of your PATH environemnt variable. In other words, you want PATH `/usr/local/bin/` to take precedence over `/usr/bin/` so that Homebrew installations will be called over the tools that Mac OS X may select automatically that could run counter to the development environment we're creating. To do so, you can create or open the `~/.bash_profile` file with the the command-line text editor **nano** using the `nano` command:

```
$ nano ~/.bash_profile
```

Once the file opens up in the Terminal window, enter the following:

```
export PATH=/usr/local/bin:$PATH
```

Hit `control + o` to save, and when prompted the `return` key. You can exit nano by hitting `control + x`.

To activate your changes you have made to the `PATH` environment variable, type the following:

```
$ source ~/.bash_profile
```

To make sure that Homebrew was successfully installed, type the following:
```
$ brew doctor
```

If no updates are required at this time, the Terminal output will read:

```
Your system is ready to brew.
```

Sometimes you will need to `brew prune` or `brew update` to correct some errors (or whatever command brew instructs you to run.)


### Step 4 - Installing Python 3

Use the `brew search` command to list Python-related packages. Python 3 should be among the items on the list. Run in the following to install:

```
$ brew install python 3
```

Confirm installation by running:

```
$ python3 --version
```

### Step 5 - Creating a Virtual Environment

1. Choose the directory you would like to put your Python programming environments in using the `cd` commands.
2. Make an *Environments* directory (or whichever name you would like to call it) via `mkdir Environments`.
3. `cd Environments` into the directory.
4. Once you're in your `Environments` directory, you can run the following command to create an environment. You can replace the *my_env* with your own environment name.

```
$ python 3.7 -m venv my_env

```

5. You can activate the environment by entering the following:

```
$ source my_env/bin/activate
```

6. Yoour prompt will be no prefixed with the name of your environment. In this case it's called `my_env`:

```
(my_env) Js-MacbookAir: ~ J$
```

7. To exit simply type `deactivate` in the terminal and hit `return`.

### Step 6 - Creating Django App in an Environment

1. In the active `my_env` environment we can install Django with **pip** which was installed with Python 3 as follows:

```
pip install django
```

2. Creating an App

```
django-admin startproject helloapp
```

3. Running the above command will install the following structure:

```
helloapp
├─helloapp
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py
```