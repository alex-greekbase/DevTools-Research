# Install Ubuntu on machine
1. download Ubuntu iso [here](https://ubuntu.com/download/desktop)

2. create Ubuntu bootable USB ([guide](https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#1-overview)) with [balenaEtcher](https://www.balena.io/etcher/) 

3. insert USB and reboot with Ubuntu option, install Ubuntu desktop ([guide](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview))

4. Step 6 Installation type manual partition option: 
    - EFI recommended 550MB (partition used for system boot)
    - Swap recommanded same size as the physical RAM (partition used as overflow space for RAM)
    - Ext4 for root mounted on /, 50GB (partition used as Linux Finesystem)
    - Ext4 for homw mounted on /home, 150GB (partition used as Linux Finesystem)

    (the two Ext4 partitions can be adjusted according to available disk space)


# Install software from store
- Slack
- VS code
- GParted
- etc.


# Install Gnome extensions
- Gnome-shell-extensions: 
    `$ sudo apt update`
    `$ sudo apt install gnome-shell-extensions`     # Gnome Shell native host connector
- [Lock Keys](https://extensions.gnome.org/extension/36/lock-keys/), use browser to toggle on the tool


# Install package managers
- npm (node package manager): `$ sudo apt install npm`
- etc.


# Install useful tools via terminal
- tree (show folder tree): `$ sudo apt-get install tree`


# Install Zsh and Vim
1. curl
    cURL, client URC, used to transfer data to and from a server

    *Install*:
        `$ sudo apt-get install curl`

2. git
    version control and source code management

    *Install*:
        `$ sudo apt-get install git`
    
    *[Configure](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)*:
        `$ git config --global user.name "Your name"`
        `$ git config --global user.email youremail@example.com`
        `$ git config --global init.defaultBranch main`

    *Check configuration*:
        `$ git config --list`
    
    *[Connect to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)*:
    1. check existing SSH keys if any: `$ ls -al ~/.ssh`
    2. generate new SSH key: `$ ssh-keygen -t ed25519 -C "your_email@example.com"`
    3. start ssh-agent: `$ eval "$(ssh-agent -s)"`
    4. add SSH private key to the ssh-agent: `$ ssh-add ~/.ssh/id_ed25519`
    5. open public key, then copy the contents to GitHub: `$ cat ~/.ssh/id_ed25519.pub`
    6. test SSH connection to GitHub, type yes to continue connecting: `$ ssh -T git@github.com`
      

3. vim
    a powerful editor

    *Install*:
        `$ sudo apt-get install vim`

    *Configure*:
    in ~/.vimrc add:
    ```
    set number
    
    set laststatus=2
    set statusline+=
    set statusline+=\%F
    set statusline+=%=
    
    set statusline+=\ %y
    set statusline+=\ %{&fileencoding?&fileenconding:&encoding}
    set statusline+=\ [%{&fileformat}]
    set statusline+=\ %p%%
    set statusline+=\ %l:%c
    set statusline+=\
    
    set tabstop=4
    set shiftwidth=4
    set expandtab
    ```

4. zsh (Z shell)
    a more powful bash 

    *Install*:
        `$ sudo apt-get update`
        `$ sudo apt-get install zsh`

    *Check zsh version*:
        `$ zsh --version`

    zsh configuration will be done by ohmyzsh
    
5. Oh My Zsh
    a community framework to manage zsh configuration

    *Install*:
        `$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
    
6. powerlevel10k
    a pretty zsh theme

    *Install*:
    1. [download](https://github.com/romkatv/powerlevel10k) and install Meslo NF font 
    2. change font to MesloLGS NF Regular in terminal preferences
    3. `$ git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k`
	
    *Configure*:
    1. in ~/.zshrc add: 
    ```
    ZSH_THEME="powerlevel10k/powerlevel10k"
    ```
    2. configure powerlevel10k with its wizard:	
        `$ zsh` or `$ p10k configure`

    *An Configuration Example*:
    |Setting|Choice|
    |---|---|
    |Prompt Style|Rainbow|
    |Character Set|Unicode|
    |Show current time|24-hour format|
    |Prompt Heads/Tails|Flat|
    |Prompt Height|Two lines|
    |Prompt Connection|Solid|
    |Prompt Frame|Right|
    |Connection & Frame color|Light|
    |Prompt Spacing|Sparse|
    |Icons|Many icons|
    |Prompt Flow|Concise|
    |Transient Prompt|No|
    |Instant prompt Mode|Verbose|

    *Meaning of Git status symbols in the theme*:
    ⇣42	    # this many commits behind the remote
    ⇡42	    # this many commits ahead the remote
    ⇠42     # this many commits behind the push remote
    ⇢42     # this many commits ahead the push remote
    ~42     # this many conflicts 
    +42     # this many staged changes 
    !42     # this many unstaged changes 
    ?42     # this many untracked files 
	
7. [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md)
    a zsh plug-in 

    *Install*:
        `$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`

    *Configure*:
    in ~/.zshrc add: 
    ```
    plugins=( [plugins...] zsh-syntax-highlighting)	
    ```

8. [zsh-completion](https://github.com/zsh-users/zsh-completions)
    a zsh plug-in 
    
    *Install*:
        `$ git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions`

    *Configure*:
    in ~/.zshrc add:
    ```
    fpath+=${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions/src
    ```
	


