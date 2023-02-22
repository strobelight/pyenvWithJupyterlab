# pyenvWithJupyterlab
Start jupyter lab with environment desired from pyenv.

The jupyterlab is installed in a virtual environment, and kernels added from your other virtual environment which will bring in modules installed in your virutal environment. Basically, if coding in say python 3.8 virtual environment, but jupyter installed in 3.10, after the browser tab starts, select the correct kernel.

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
* `pyenv shell jupyter`
* `pip install jupyterlab jupyter_nbextensions_configurator`
* `pyenv shell -`

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
