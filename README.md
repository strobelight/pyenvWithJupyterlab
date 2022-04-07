# pyenvWithJupyterlab
Start jupyter lab with environment desired from pyenv.

## Pre-requisites
* python
* pyenv
* pyenv virtualenv
* bash and typical unix tools
* $HOME/bin to contain scripts

## Installation
* `mkdir $HOME/bin`
* copy startJupyter and pypath to $HOME/bin
* `cd $HOME/bin`
* `chmod +x *`

## Establish jupyter environment
* `pyenv virtualenv 3.10.3 jupyter` # pick another python 3 version if you like
* `pyenv local jupyter`
* `pip install jupyterlab`

## Start jupyter
* `cd your-project`
* this directory should have a .python-version file
* `$HOME/bin/startJupyter`  # browser should open

## Start jupyter via applescript
```
set loc to choose folder with prompt " What directory should jupyter be run from? " 
set pLoc to quoted form of POSIX path of loc as string 
do shell script "cd " & pLoc & "; $HOME/bin/startJupyter"
```

## Troubleshooting
* if run via Applescript, check /tmp/jupyter.log
