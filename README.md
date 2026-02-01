## Some Installs

- [Docker Images : Maintain for AWS & GCP](https://hub.docker.com/u/prodrelworks)
- [https://docs.docker.com/develop/develop-images/multistage-build/](https://docs.docker.com/develop/develop-images/multistage-build/)
- [https://gist.github.com/azmarifdev/9c16c5a33e93aee05b35147fe7da1015](https://gist.github.com/azmarifdev/9c16c5a33e93aee05b35147fe7da1015)
- [https://gist.github.com/n1snt/454b879b8f0b7995740ae04c5fb5b7df](https://gist.github.com/n1snt/454b879b8f0b7995740ae04c5fb5b7df)
- [https://ohmyz.sh/#install](https://ohmyz.sh/#install)
- [https://ohmyposh.dev/docs/installation/linux](https://ohmyposh.dev/docs/installation/linux)
- [https://catalins.tech/zsh-plugins/](https://catalins.tech/zsh-plugins/)
- [https://gist.github.com/mohanpedala/1e2ff5661761d3abd0385e8223e16425?permalink_comment_id=3945021](https://gist.github.com/mohanpedala/1e2ff5661761d3abd0385e8223e16425?permalink_comment_id=3945021)
- [https://tmuxcheatsheet.com/theming-and-customizing/](https://tmuxcheatsheet.com/theming-and-customizing/)

```bash
git clone --depth 1 -- https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone --depth 1 -- https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
git clone --depth 1 -- https://github.com/zdharma-continuum/fast-syntax-highlighting.git $ZSH_CUSTOM/plugins/fast-syntax-highlighting
git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git $ZSH_CUSTOM/plugins/zsh-autocomplete
git clone --depth 1 -- https://github.com/agkozak/zsh-z $ZSH_CUSTOM/plugins/zsh-z
git clone https://github.com/fdellwing/zsh-bat.git $ZSH_CUSTOM/plugins/zsh-bat

git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install

plugins=(
    fzf
    git
    sudo
    history-substring-search
    colored-man-pages
    zsh-autosuggestions
    zsh-syntax-highlighting
    fast-syntax-highlighting
    zsh-autocomplete
    zsh-z
)
```

## TMUX Setup

- [https://tmuxcheatsheet.com/theming-and-customizing/](https://tmuxcheatsheet.com/theming-and-customizing/)
- [https://github.com/tmux-plugins/tpm](https://github.com/tmux-plugins/tpm)

```bash
# Customizing TMUX
# git clone <https://github.com/tmux-plugins/tpm> ~/.tmux/plugins/tpm

# List of plugins
set -g @plugin 'tmux-plugins/tmux-battery'
set -g @plugin 'tmux-plugins/tmux-cpu'
set -g @plugin 'tmux-plugins/tmux-online-status'
set -g @plugin 'tmux-plugins/tmux-sidebar'
set -g @plugin 'tmux-plugins/tmux-resurrect'
# set -g @plugin 'erikw/tmux-powerline'
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'

# Address vim mode switching delay (<http://superuser.com/a/252717/65504>)
set -s escape-time 0

# Increase scrollback buffer size from 2000 to 50000 lines
set -g history-limit 60000

# Increase tmux messages display duration from 750ms to 4s
set -g display-time 2000

# Refresh 'status-left' and 'status-right' more often, from every 15s to 5s
set -g status-interval 5

# (OS X) Fix pbcopy/pbpaste for old tmux versions (pre 2.6)
# set -g default-command "reattach-to-user-namespace -l $SHELL"

# Upgrade $TERM
set -g default-terminal "tmux-256color"
set -as terminal-overrides ',*:Tc'
# set -g default-terminal "screen-256color"

# Emacs key bindings in tmux command prompt (prefix + :) are better than
# vi keys, even for vim users
# set -g status-keys emacs

# Focus events enabled for terminals that support them
set -g focus-events on

# Super useful when using "grouped sessions" and multi-monitor setup
setw -g aggressive-resize on

# Use mouse interactively on the screen
set -g mouse

# Configure the catppuccin plugin
set -g @catppuccin_flavor "mocha" # latte, frappe, macchiato, or mocha
set -g @catppuccin_window_status_style "rounded" # basic, rounded, slanted, custom, or none

# Load catppuccin
run /local/mnt/workspace/sumilahi/.config/tmux/plugins/catppuccin/catppuccin.tmux

# Make the status line pretty and add some modules
set -g status-right-length 100
set -g status-left-length 100
set -g status-left ""
set -g status-right "#{E:@catppuccin_status_application}"
set -agF status-right "#{E:@catppuccin_status_cpu}"
set -ag status-right "#{E:@catppuccin_status_session}"
set -ag status-right "#{E:@catppuccin_status_uptime}"
set -agF status-right "#{E:@catppuccin_status_battery}"

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'

# run /local/mnt/workspace/sumilahi/.config/tmux/plugins/catppuccin/tmux/catppuccin.tmux
# run /local/mnt/workspace/sumilahi/.config/tmux/plugins/catppuccin/tmux/catppuccin.tmux
```

### TMUX Source Env

```bash
tmux source-file ~/.tmux.conf
```


## Language Server

- [https://dev.languagetool.org/http-server](https://dev.languagetool.org/http-server)

```bash
# Run from the server docker container.
java -cp languagetool-server.jar org.languagetool.server.HTTPServer --config $HOME/server.properties --port 8081 --allow-origin --public

# Check in browser.
http://localhost:8082/v2/check?language=en-US&text=my+text
```

## TexLive

- [https://www.tug.org/texlive/quickinstall.html](https://www.tug.org/texlive/quickinstall.html)
- [https://www.tug.org/texlive/]
- [https://inkscape.org/](https://inkscape.org/)
- [https://textext.github.io/textext/](https://textext.github.io/textext/)
- 

## Initial Install :

```bash

sudo apt-get install -y \
    curl wget cmake git nano make \
    build-essential ca-certificates z3 python3 nginx python3-pip \
    llvm z3 gcc g++ golang-go gccgo ninja-build libgraphviz-dev \
    libgmp-dev libmpfr-dev clang libboost-all-dev python3-pip \
    autoconf less vim gcc-multilib sudo ca-certificates guake graphviz \
    libgraphviz-dev python3-pygraphviz lcov ggcov apt-utils net-tools \
    inotify-tools gnupg-agent software-properties-common libstdc++-10-dev inotify-tools \
    apt-transport-https curl gnupg-agent software-properties-common dafny z3 \
    build-essential curl libcap-dev git cmake libncurses5-dev python3 \
    python3-pip unzip libtcmalloc-minimal4 libgoogle-perftools-dev \
    libsqlite3-dev doxygen gcc-multilib g++-multilib \
    clang-9 llvm-9 llvm-9-dev llvm-9-tools afl++

sudo pip3 install lit tabulate wllvm pygame keras pandas scikit-learn 
sudo pip3 install torch torchvision
curl -OL https://github.com/google/googletest/archive/release-1.7.0.zip
unzip release-1.7.0.zip
```
## Basic Setup 

```bash
sudo snap install htop
sudo snap install --classic heroku
sudo snap install microk8s --channel=1.19/candidate --classic
sudo snap install slack --classic
sudo snap install gitkraken --classic

# Installing JAVA
sudo apt-get install default-jdk default-jre

# Full Tex Libraries
sudo apt-get install texlive-full texmaker xournal

# Node.js
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## Docker Install  : 

- [https://docs.docker.com/desktop/setup/install/linux/](https://docs.docker.com/desktop/setup/install/linux/)
- [https://www.docker.com/](https://www.docker.com/)
- [https://docs.docker.com/build/](https://docs.docker.com/build/)

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
sudo apt update

apt-cache policy docker-ce
sudo apt install -y docker-ce

sudo usermod -aG docker $USER
sudo systemctl status docker
```

## Docker Example

```bash
docker buildx build -t win1-dev-machine:25.10 -f .\windows.dockerfile .

docker run -d --name dev1-clang-llvm --restart unless-stopped `
  -p 8080:8080 -p 8081:80 -p 443:443 -p 2025:22 -p 5056:56 -p 8082:8081 -p 3000:3000 -p 2000:2000 -p 5000:5000 `
  --hostname=5b3f3926b12d `
  --env FULLNAME=dev1-clang-llvm `
  --env PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin" `
  --volume "C:\Users\lahir\Documents:/docs" `
  --volume "C:\Users\lahir\Documents\workdir:/workdir" `
  --volume "C:\Users\lahir\Downloads:/downloads" `
  --volume dev1-persistance:/persist `
  --network=bridge `
  --label "org.opencontainers.image.ref.name=ubuntu" `
  --label "org.opencontainers.image.version=25.10" `
  win1-dev-machine:25.10
```


## More Packages : 

```bash 
sudo apt-get install gparted

sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" \ 
    > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install postgresql-client-12 pgadmin4 nginx openssh-server libstdc++-10-dev
sudo apt-get upgrade
sudo update-initramfs -u
sudo update-grub
sudo update-grub2
```

```bash
CC=clang CXX=clang++                            \
cmake -DCMAKE_INSTALL_PREFIX=/usr               \
      -DLLVM_ENABLE_FFI=ON                      \
      -DCMAKE_BUILD_TYPE=Release                \
      -DLLVM_ENABLE_PROJECTS="clang;compiler-rt" \
      -DLLVM_BUILD_LLVM_DYLIB=ON                \
      -DLLVM_LINK_LLVM_DYLIB=ON                 \
      -DLLVM_ENABLE_RTTI=ON                     \
      -DLLVM_TARGETS_TO_BUILD="X86;ARM;host;AMDGPU;BPF" \
      -DLLVM_BUILD_TESTS=ON                     \
      -Wno-dev -G Ninja ../llvm                &&
ninja all
```
## Lighter Build

```bash
cmake \
    -S llvm -B build -Wno-dev -GNinja \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DLLVM_ENABLE_PROJECTS="libcxx;libcxxabi;clang;compiler-rt" \
    -DLLVM_ABI_BREAKING_CHECKS=FORCE_OFF \
    -DCMAKE_BUILD_TYPE=Release \
    -DLLVM_TARGETS_TO_BUILD="X86" \
    -DLLVM_ENABLE_RTTI=ON \
    -DLLVM_ENABLE_FFI=ON \
    -DLLVM_BUILD_TESTS=ON \
    -DLLVM_INSTALL_UTILS=ON
```

Other `Ubuntu 20.04` Installs :

- Inkscape with TexText : [Inkscape TexText](https://textext.github.io/textext/install/linux.html)
- Bluetooth Issue : [Install](https://askubuntu.com/questions/922860/pairing-apple-airpods-as-headset)
- GOLLVM Commit : [Issue Install](https://go.googlesource.com/gollvm/+/9e1280ddbe7c442191b630827c030d13de35b569)
- TexStudio : [Install](https://linuxhint.com/install-texstudio-latex-editor-linux/)
- Fortinet Client : [Install](https://links.fortinet.com/forticlient/deb/vpnagent)
- Zoom Client : [Install](https://zoom.us/download?os=linux)
- JAVA Install : [DigitalOcean Guide](https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-on-ubuntu-18-04)

## More Build CMD for `cmake-projects` for Research Projects : (KLEE-LLVM-COV)

```bash
export HOME=/home

# LLVM 10, clang-10 build
git clone https://github.com/klee/klee-uclibc.git
cd klee-uclibc
./configure --make-llvm-lib --with-llvm-config $(which llvm-config-10) --with-cc $(which clang-10) --enable-assertions --enable-release
make -j 8
   
mkdir libcxx-build
cd ./klee

LLVM_VERSION=10 BASE=$HOME/libcxx-build REQUIRES_RTTI=1 DISABLE_ASSERTIONS=1 \
    ENABLE_DEBUG=0 ENABLE_OPTIMIZED=1 ./scripts/build/build.sh libcxx

cd ../
mkdir klee-build && cd ./klee-build

cmake \
  -DENABLE_POSIX_RUNTIME=ON \
  -DENABLE_KLEE_UCLIBC=ON \
  -DKLEE_UCLIBC_PATH=$HOME/klee-uclibc \
  -DLLVM_CONFIG_BINARY=$(which llvm-config-10) \
  -DLLVMCC=$(which clang-10) \
  -DLLVMCXX=$(which clang++-10) \
  -DENABLE_KLEE_LIBCXX=ON \
  -DENABLE_KLEE_EH_CXX=ON \
  -DKLEE_RUNTIME_BUILD_TYPE=Release+Debug+Asserts \
  -DKLEE_LIBCXX_DIR=$HOME/libcxx-build/libc++-install-90/ \
  -DKLEE_LIBCXXABI_SRC_DIR=$HOME/libcxx-build/llvm-90/libcxxabi/ \
  -DKLEE_LIBCXX_INCLUDE_DIR=$HOME/libcxx-build/libc++-install-90/include/c++/v1/ \
  -DENABLE_KLEE_EH_CXX=ON \
  -DENABLE_UNIT_TESTS=ON \
  -DGTEST_SRC_DIR=$HOME/googletest-release-1.7.0/ $HOME/klee
  
make -j 4
make install 
```

## Termification : 

```bash
sudo apt install -y golang-go unzip git wget
go get -u github.com/justjanne/powerline-go

wget https://github.com/microsoft/cascadia-code/releases/download/v2009.22/CascadiaCode-2009.22.zip
unzip CascadiaCode-2009.22.zip

sudo cp -r ttf/ /usr/share/fonts/
sudo cp -r woff2/ /usr/share/fonts/

sudo nano ~/.bashrc

GOPATH=$HOME/go
function _update_ps1() {
    PS1="$($GOPATH/bin/powerline-go -error $?)"
}
if [ "$TERM" != "linux" ] && [ -f "$GOPATH/bin/powerline-go" ]; then
    PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"
fi
```

* [Cascadia Code PL](https://github.com/microsoft/cascadia-code/releases?WT.mc_id=-blog-scottha)
* [Terminal Schemes](https://docs.microsoft.com/en-us/windows/terminal/custom-terminal-gallery/frosted-glass-theme)
* [Retro Fitting](https://docs.microsoft.com/en-us/windows/terminal/custom-terminal-gallery/retro-command-prompt)
* [Language-Tool](https://dev.languagetool.org/http-server)

## Running MacOSX : 

```bash
sudo docker run --name macosx \
    --device /dev/kvm \
    --device /dev/snd \
    -e AUDIO_DRIVER=pa,server=unix:/tmp/pulseaudio.socket \
    -v "/run/user/$(id -u)/pulse/native:/tmp/pulseaudio.socket" \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -e PULSE_SERVER=unix:/tmp/pulseaudio.socket \
    --privileged \
    --net host \
    --cap-add=ALL \
    -e SMP=4 \
    -e CORES=4 \
    -e RAM=16 \
    -p 50922:10022 \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -e EXTRA='-usb -device usb-host,hostbus=1,hostaddr=2' \
    -v /dev:/dev \
    -v /lib/modules:/lib/modules \
    -e "DISPLAY=${DISPLAY:-:0.0}" \
    sickcodes/docker-osx:latest
```
## Pen-Input Settings : 

```bash
$ xrandr
$ xinput map-to-output 23 HDMI-0
```

## Interesting & Frequent Commands :  

- Random Text generation : 
    - `$(tr -dc 'A-Za-z0-9' </dev/urandom | head -c 15)`

- Kill A Process by name : 
    - `$(sudo kill -15 $(ps -aux | grep $1 | awk '{ print $2 }'))`

- Epoll Source : 
    - [Epoll](https://github.com/enki/libev/blob/master/ev_epoll.c) 

- Get a series of zeros or null file : 
    - `head -c 100 /dev/zero > input05.txt`

- Dwarf Information : 
    - `ELFs & Dwarfs` [Good Intro](http://www.dwarfstd.org/doc/Debugging%20using%20DWARF-2012.pdf)

- Get Random data dump of "n" bytes : Change `bs` value
    - ` dd if=/dev/random of=input01.txt bs=16 count=1`
   
- LLVM Program 
    - `find . -regex '.*\.\(cpp\|hpp\|cu\|c\|h\)' -exec clang-format -style=file -i {} \;`

- Git Commands

```bash
git config credential.helper 'cache --timeout=300'
git config --global commit.gpgsign false
git diff > diff.patch
git apply diff.patch

git config --global user.email <email>
git config --global user.name <name>
git config --global color.ui true
git config --global core.editor "nano -w -n"
git config --global credential.helper store
```

## Powershell Example

```pwsh
Get-ChildItem -Path . -File |
  Where-Object { $_.Name -like 'Happy Cat 😺(*' } |
  ForEach-Object {
    $newName = $_.Name -replace '^Happy Cat 😺\(', 'MumMumNew'
    Rename-Item -LiteralPath $_.FullName -NewName $newName  # add -WhatIf first to preview
}
```
