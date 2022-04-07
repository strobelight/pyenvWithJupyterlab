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

## Add jupyter environment to your project
* `cd your-project`
* `pyenv local`  # note the current environment
* `pyenv local your-current-env jupyter`  # add jupyter env
* `cat .python-version` should now show at least two

## Start jupyter
* $HOME/bin/startJupyter  # browser should open
