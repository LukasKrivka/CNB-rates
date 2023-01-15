# Czech National Bank (CNB) official foreign exchange rates scraper

The official exchange rates for CZK can be found at https://www.cnb.cz/cs/financni-trhy/devizovy-trh/kurzy-devizoveho-trhu/kurzy-devizoveho-trhu/rok_form.html
This script scrapes the data for a custom time range, as long as the requested years are available (currently 1991 - 2023).

The requirements are python 3+ (development version 3.9.6 should be garanteed to work) and packages listed in requirements.txt 
(pandas, requests and dependencies).

The script can be used as separate mini-module, which is why the __init__.py file is included. To import it, 
make sure the module's directory is included in PYTHONPATH. More in practical information on this is in notes.txt.

The main.py file shows en example how it could be used to export the data to csv file

### Black Box Solution
For those that are not interested in the inner workings or even do not want to understand and simply need the output, 
there is a prepared blackbox solution for MacOS/Linux.

* In the Terminal application, verify that git is installed, by running:
```bash
which git
```
This should output something like: usr/bin/git.
If the output says _git not found_, **git** is not installed. Possible fix with **homebrew**:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
followed by:
```bash
brew install git
```
The installaiton might take a minute. You will be prompted for your password.

* Next, make a clone of this repository:
This default solution will create a folder in your Desktop, where everything happens
```bash
cd Desktop
git clone https://github.com/LukasKrivka/CNB-rates
```

* Finally, run a prepared bash script.
```bash
cd CNB-rates
bash simple_run.sh
```
This will handle everything else (python environment, packages, and execution).
The default option for this method is filled dataset - which means the missing dates (weekends etc.) are going to be filled with previous value.
The exported csv should appear in the CNB-rates file. Then you can move it to your desired location and delete the rest of the file.

### Final remarks:
This script was developed mainly for my own needs. I am not necessarily planing on extending functionality (like sql connection) or maintaining support for subsequent dependencies releases. Noting in this script or reposiory is guaranteed.
