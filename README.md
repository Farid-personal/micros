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
    Makefile: has the steps of the project life cycle
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