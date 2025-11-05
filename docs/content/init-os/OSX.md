# Initiate OSX

---

### Common

###### Install OSX:

https://support.apple.com/vi-vn/102662#terminal

###### Set hostname:

```shell
sudo scutil --set HostName My~MacBook~Pro
sudo scutil --set ComputerName My~MacBook~Pro
sudo scutil --set LocalHostName My~MacBook~Pro
```

###### `ll` command by alias:

```shell
echo "alias ll='ls -lGa'" >> ~/.zprofile
```

###### Install Xcode Command Line Tools:

***Note: This is a heavy task***

***Note 2: These tools already contain: git***

```shell
xcode-select --install
```

---

### Homebrew based

###### Install Homebrew

Install Homebrew

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Add Homebew to PATH (Show in `Next step` of output log after install Homebrew):

```shell
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Disable Homebrew analytics

```shell
brew analytics off
```

###### Install software by Homebrew

- Install [iTerm 2](https://iterm2.com/):

    ```shell
    brew install --cask iterm2
    ```

- Install watch from [procps](https://gitlab.com/procps-ng/procps):

    ```shell
    brew install watch
    ```

- Install [Python build dependencies](https://devguide.python.org/getting-started/setup-building/#macos):

    ```shell
    brew install pkg-config openssl@3.0 xz gdbm tcl-tk
    ```

- Install Java Development Kit (JDK)

    Search for available JDK version:

    ```shell
    brew search jdk
    #brew search openjdk
    ```

    Install specific JDK version:

    - Open JDK 17:

        ```shell
        brew install openjdk@17
        ```

        ```shell
        brew info openjdk@17
        ```

        For the system Java wrappers to find this JDK, symlink it with:

        ```shell
        sudo ln -sfn /opt/homebrew/opt/openjdk@17/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-17.jdk
        ```

        Add JDK to PATH:

        ```shell
        echo 'export PATH="/opt/homebrew/opt/openjdk@17/bin:$PATH"' >> ~/.zshrc
        ```

        For compilers to find openjdk@17 you may need to set:

        ```shell
        echo 'export CPPFLAGS="-I/opt/homebrew/opt/openjdk@17/include:$CPPFLAGS"' >> ~/.zshrc
        ```
    
    Find the Java home:

    ```shell
    /usr/libexec/java_home -V
    ```

    Set the JAVA_HOME environment variable:

    ```shell
    echo 'export JAVA_HOME="/Library/Java/JavaVirtualMachines/openjdk-17.jdk/Contents/Home"' >> ~/.zshrc
    #echo 'export PATH=$PATH:$JAVA_HOME/bin' >> ~/.zshrc
    ```

- Install [Coursier](https://get-coursier.io/) and [Scala](https://www.scala-lang.org/):

    1. Install [Coursier](https://get-coursier.io/docs/cli-installation):

        ```shell
        brew install coursier/formulas/coursier
        cs setup
        ```
    
    2. Install [Scala](https://www.scala-lang.org/):
    
        ```shell
        cs install scala:2.12.18 && cs install scalac:2.12.18
        ```

- Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/):

    ```shell
    brew install --cask miniconda
    #brew install --cask anaconda
    ```

    Create an environment named `myenv` with python 3.12 and containing the package 'sqlite':

    ```shell
    conda create -n myenv python=3.12 sqlite
    ```

    Remove all packages from environment `myenv` and the environment itself:

    ```shell
    conda remove -n myenv --all
    ```

    Disable auto activate `base` environment:

    ```shell
    conda config --set auto_activate_base false
    ```

- Install [NodeJS](https://nodejs.org/):

    ```shell
    brew install node
    ```

- Install [Dbeaver](https://dbeaver.io/):

    ```shell
    brew install --cask dbeaver-community
    ```

- Install [k3d](https://k3d.io/):

    ```shell
    brew install k3d
    ```

- Install [kubectl](https://kubernetes.io/docs/reference/kubectl/):

    ```shell
    brew install kubectl
    ```

- Install [Helm](https://helm.sh/):

    ```shell
    brew install helm
    ```

- Install [yq](https://mikefarah.gitbook.io/yq):

    ```shell
    brew install yq
    ```

- Install [jq](https://jqlang.org/):

    ```shell
    brew install jq
    ```

- Install [postgresql](https://www.postgresql.org/download/macosx/) for development:

    ```shell
    brew install postgresql
    ```

---

### Other installations

##### Command line based

- Install [Rust](https://www.rust-lang.org/):

    ```shell
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
    ```

###### pyvenv based

- Install [JupyterLab](https://jupyterlab.readthedocs.io/en/latest/getting_started/installation.html#pip):

    ```shell
    # source .venv/bin/active
    pip install jupyterlab
    ```

##### UI installation based

###### App Store based

- [ShellFish](https://apps.apple.com/vn/app/ssh-files-secure-shellfish/id1336634154)

- [Keka](https://apps.apple.com/vn/app/keka/id470158793)

- [Folx GO+](https://apps.apple.com/vn/app/folx-go/id823528286)

- [Amphetamine](https://apps.apple.com/vn/app/amphetamine/id937984704) with [Amphetamine Enhancer](https://github.com/x74353/Amphetamine-Enhancer/raw/master/Releases/Current/Amphetamine%20Enhancer.dmg) (Download suggested from application)

- [iStat Menus](https://apps.apple.com/vn/app/istat-menus/id1319778037) with [iStat Menus Helper](https://cdn.bjango.com/files/istatmenushelper/istatmenushelper2.0.zip) (Download suggested from application)

- [Magnet](https://apps.apple.com/vn/app/magnet/id441258766)

- [Lich van nien](https://apps.apple.com/vn/app/l%E1%BB%8Bch-v%E1%BA%A1n-ni%C3%AAn-%C3%A2m-l%E1%BB%8Bch-vn/id1463023539)

- [Microsoft Word](https://apps.apple.com/vn/app/microsoft-word/id462054704)

- [Microsoft Excel](https://apps.apple.com/vn/app/microsoft-excel/id462058435)

- [Microsoft PowerPoint](https://apps.apple.com/vn/app/microsoft-powerpoint/id462062816)

- [Microsoft OneNote](https://apps.apple.com/vn/app/microsoft-onenote/id784801555)

- [OneDrive](https://apps.apple.com/vn/app/onedrive/id823766827)

- [Windows App (Previously Microsoft Remote Desktop)](https://apps.apple.com/vn/app/windows-app/id1295203466)

- [Jump Desktop](https://apps.apple.com/vn/app/jump-desktop-rdp-vnc-fluid/id524141863)

- [Maccy](https://apps.apple.com/vn/app/maccy/id1527619437)

- [UTM Virtual Machine](https://apps.apple.com/vn/app/utm-virtual-machines/id1538878817)

- [Presentify - Screen Annotation](https://apps.apple.com/vn/app/presentify-screen-annotation/id1507246666)

- [Photomator](https://apps.apple.com/vn/app/photomator/id1444636541)

- [Pixelmator Pro](https://apps.apple.com/vn/app/pixelmator-pro/id1289583905)

- [Final Cut Pro](https://apps.apple.com/vn/app/final-cut-pro/id424389933)

- [DaVinci Resolve Studio](https://apps.apple.com/vn/app/davinci-resolve-studio/id900392332)

###### Manually download and install

- [Adguard](https://adguard.com/en/adguard-mac/overview.html)

- [Bartender](https://www.macbartender.com/)

- [NotchNook](https://lo.cafe/notchnook)

- [FileZilla](https://filezilla-project.org/download.php?platform=osx)

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)

- [VSCode](https://code.visualstudio.com/download)

- [JetBrains Toolbox App](https://www.jetbrains.com/toolbox-app/)

- [Parallels Desktop](https://www.parallels.com/products/desktop/)

- [VMWare Fusion](https://download3.vmware.com/software/FUS-1302/VMware-Fusion-13.0.2-21581413_universal.dmg)

- [XMind 8](https://dl3.xmind.net/xmind-8-update9-macosx.dmg) with (optional) [template](https://xmind.app/blog/mind-map-presentation-template/)
