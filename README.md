Install ubuntu 20.04.6 LTS from store
Install windows terminal

- test ubuntu (window poweshel):
    PS C:\Users\fa> wsl -l -v
    ---------------------------------------------
    wsl -l -v
    NAME            STATE           VERSION
    Ubuntu-22.04    Running         2
    ---------------------------------------------

    This will install ubuntu 

    if wsl -l -v fails:
    powershell (run as admin): wsl --install (maybe restart)
    wsl --set-version Ubuntu-22.04 2
    https://medium.com/python-mvp/upgrade-python-3-10-to-3-11-on-ubuntu-22-04-2f63e4d326f9


 - isntall python3.11 in local ubuntu:
    sudo apt install -y python3.11
    sudo add-apt-repository ppa:deadsnakes/ppa
    sudo apt-get update
    sudo apt install -y python3.11
    sudo apt install -y python3.11-venv
    sudo apt install -y python3-pip
    sudo apt install -y python3.11-dev

- create a virtual env:
    python3.11 -m venv ~/mic
    pip install --upgrade pip

- Add sourcing to baschrc so that mic venv becomes the default env of ubuntu
    add these lines at the end of ~/.bachrc
        #sourcing python venv                                                                              
        source ~/mic/bin/activate 

- Create a git account with a new repository

- Config Git in powershell
    git config --global user.name "faridhazad"
    git config --global user.email "farid.azad@troo.com"
    git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager.exe"
    Tested: git clone https://github.com/TrooCorp/layer-processor.git

 - Config Git in Linux:
    git config --global user.name "faridhazad"
    git config --global user.email "farid.azad@troo.com"
    git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager.exe"
    add these lines to  /usr/bin/git-credential-manager
    
    ---------------------------------------------
    #!/bin/sh 
    exec "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager.exe" $@
    git config --add credential.helper manager
    ---------------------------------------------

- download the repository from git
    git clone https://github.com/Farid-personal/micros.git

- start vs from the folder: (mic) fazad@DESKTOP-DOIBIBS:/mnt/c/Development/micros$/code .
- add python extention and python manager extention

- set python in vs (vs termimal):
    which python:   /home/fazad/mic/bin/python
    ctrl + shift in vs >> select interpretor >> find python in venv mic (path above)

- empty file list:
    requirements.txt: install commands for packages used in this code
    Dockerfile
    Makefile: has the steps of the project life cycle. a tool to keep the project organized.
    main.py: runs the 
    mylib/__main__.py: helps python import the library

- create empty files (vs termimal or ubuntu):
    create a new branch
    touch requirements.txt
    touch Dockerfile
    touch Makefile
    mkdir mylib (your code library)
    
    in oder to python to be able to import the library you need the below:
        touch mylib/__init__.py
    
    put the actual source code:
        touch mylib/logic.
    
    microservice built-out file:
        touch main.py (this imports the library code)

- add sections to make file:
    install:
        # install commands
    format:
        # format code
    lint:
        # flake8 or pythlint
    test: 
        # test
    deploy:
        #deploy

    all: install lint test deploy

- try 'make' command (vs termimal or ubuntu):
    (mic) fazad@DESKTOP-DOIBIBS:/mnt/c/Development/micros$ make install 
    (mic) fazad@DESKTOP-DOIBIBS:/mnt/c/Development/micros$ make all 

- add packages to requirements.txt 
    wikipedia
    pytest
    pytest-cov
    pylint
    black # formatting tool
    fire

- add commands to makefile to install them in the venv
    pip install --upgrade pip &&\
    pip install -r requirements.txt

- run 'make install' to install all packages in requirements.txt 

- add version numbers of the install packages to the requirements.txt 
    this is necessary to make sure all installs in the future will be same as now.

    run 'pip freeze' or find the packages in python extention (export environmet on the venv)

    replace all in requirements.txt with this:
        wikipedia==1.4.0
        pytest==8.3.5
        pytest-cov==6.1.1
        pylint==3.3.7
        black==25.1.0  # formatting tool
        fire==0.7.0


