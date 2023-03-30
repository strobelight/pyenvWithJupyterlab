# pyenvWithJupyterlab
Start jupyter notebook with environment desired from pyenv.

The jupyterlab and notebook is installed in a virtual environment, and kernels added from your other virtual environment which will bring in modules installed in your virutal environment. Basically, if coding in say python 3.8 virtual environment, but jupyter installed in 3.10, after the browser tab starts, select the correct kernel.

Startup time is increased the first time a jupyter environment is created from your current virtual environment. This is done in order that your current virtual environment is not tainted with extra modules from the installation of modules to support jupyter.

## Pre-requisites
* python
* pyenv
* pyenv virtualenv
* bash and typical unix tools
* $HOME/bin to contain scripts

## Installation
* `mkdir $HOME/bin`
* copy startJupyter, createJupyter, and pypath to $HOME/bin
* `cd $HOME/bin`
* `chmod +x *`

## Establish jupyter environment
* `createJupyter [python-version]`  # defaults to 3.10.6

## Start jupyter
* `cd your-project`
* this directory should have a .python-version file, if not establish one via `pyenv local <some_virtual_env>`
* `$HOME/bin/startJupyter`  # browser should open

## Start jupyter via applescript
```
set loc to choose folder with prompt " What directory should jupyter be run from? " 
set pLoc to quoted form of POSIX path of loc as string 
do shell script "cd " & pLoc & "; $HOME/bin/startJupyter"
```

## Troubleshooting
* if run via Applescript, check /tmp/jupyter.log
* there should only be one jupyter
