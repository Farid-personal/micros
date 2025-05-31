Install ubuntu 20.04.6 LTS from store
Install windows terminal

- test ubuntu (window poweshel):
wsl -l -v


This will install ubuntu (wsl -l -v fails):
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

2. add sourcing to baschrc so that mic venv becomes the default env of ubuntu
    add these lines at the end of ~/.bachrc
        #sourcing python venv                                                                              
        source ~/mic/bin/activate 

3.create a git account with a new repository and download the repo into a folder
4. start vs from the folder: (mic) fazad@DESKTOP-DOIBIBS:/mnt/c/Development/micros$/code .
5. add python 
3. autorize vs:
    farid-personal is the git user name

    git config --global user.name "farid-personal"
    git config --global user.email "faridazadh@gmail.com"
    git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager.exe"

3.
