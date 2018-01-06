### Required Software Installations
<dl>
    <dt>The Firefox web browser</dt>
    <dd>Selenium can actually drive any of the major browsers, but Firefox is the best to use as an example because it’s reliably cross-platform and, as a bonus, is less sold out to corporate interests.</dd>
    <dt>The Git version control system</dt>
    <dd>This is available for any platform, at http://git-scm.com/. On Windows, this comes with the Bash command line, which is needed for the book.</dd>
    <dt>A virtualenv with Python 3, Django 1.11, and Selenium 3 in it</dt>
    <dd>Python’s virtualenv and pip tools now come bundled with Python 3.4+ (they didn’t always used to, so this is a big hooray). Detailed instructions for preparing your virtualenv follow.</dd>
    <dt>Geckodriver</dt>
    <dd>This is the driver that will let us remotely control Firefox via Selenium. I’ll point to a download link in Installing Firefox and Geckodriver.</dd>
</dl>

### Installing Firefox and Geckodriver
Firefox is available as a download for Windows and macOS from https://www.mozilla.org/firefox/. On Linux, you probably already have it installed, but otherwise your package manager will have it.

Geckodriver is available from https://github.com/mozilla/geckodriver/releases. You need to download and extract it and put it somewhere on your system path.

- For Windows, you can just put it in the same folder as your code for this book, or if you put it in your Python Scripts folder it’ll be available for other projects.

- For macOS or Linux, one convenient place to put it is /usr/local/bin (you’ll need sudo for this).

To test that you’ve got this working, open up a Bash console and you should be able to run:

```
$ geckodriver --version
geckodriver 0.19.1

The source code of this program is available at
https://github.com/mozilla/geckodriver.

This program is subject to the terms of the Mozilla Public License 2.0.
You can obtain a copy of the license at https://mozilla.org/MPL/2.0/.
```

### Setting Up Your Virtualenv
A Python virtualenv (short for virtual environment) is how you set up your environment for different Python projects. It allows you to use different packages (e.g., different versions of Django, and even different versions of Python) in each project. And because you’re not installing things system-wide, it means you don’t need root permissions.

Let’s create a Python 3 virtualenv called "superlists"[2] I’m assuming you’re working in a folder called python-tdd-book, but you can name your work folder whatever you like. Stick to the name "virtualenv" for the virtualenv though.

*on Windows:*
```
$ cd python-tdd-book
$ py -3.6 -m venv virtualenv
```
On Windows the py executable is a shortcut for different Python versions. On Mac or Linux we use python3.6:

*on Mac/Linux:*
```
$ cd python-tdd-book
$ python3.6 -m venv virtualenv
```

### Installing Django and Selenium
We’ll install Django 1.11 and the latest Selenium, Selenium 3.

Remember to make sure your virtualenv is active first!

```
(virtualenv) $ pip install "django<1.12" "selenium<4"
Collecting django==1.11.7
  Using cached Django-1.11.7-py2.py3-none-any.whl
Collecting selenium<4
  Using cached selenium-3.7.0-py2.py3-none-any.whl
Installing collected packages: django, selenium
Successfully installed django-1.11.7 selenium-3.7.0
```