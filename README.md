# @ How To set up the automatic driver downloader :

#### -> First of all, you need to install the appropriate Python package by typing this command in your terminal :

```bash

pip install webdriver-manager==4.0.0  // for Windows

pip3 install webdriver-manager==4.0.0  // for Mac / Linux Distros

```


#### -> Now, you need to import the package in your Python script, by adding this line at the top of your script :
##### (Note you can find these lines in the main.py file in this repository)

```python

from webdriver_manager.chrome import ChromeDriverManager

```

#### -> Finally, you need to replace this line in your script by the line down below, to automatically download the appropriate driver for your Chrome version :

```python

#-> The Old Lines :

# ** The Webdriver Options:
options = Options()
service = Service(executable_path=DRIVER_PATH)


#-> The New Lines :
options = Options()
service = Service(ChromeDriverManager().install())

# Basically, `executable_path=DRIVER_PATH` will be replaced with `ChromeDriverManager().install()`
# You can - if you want - delete the `  DRIVER_PATH = r"/usr/local/bin/chromedriver"  ` line, if you want.

```