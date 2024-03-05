# Initiate OSX

---

### Common

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

Disable Homebrew analytics

```shell
brew analytics off
```

###### Install software by Homebrew

1. Install [iTerm 2](https://iterm2.com/):

    ```shell
    brew install --cask iterm2
    ```

2. Install [Python build dependencies](https://devguide.python.org/getting-started/setup-building/#macos):

    ```shell
    brew install pkg-config openssl@3.0 xz gdbm tcl-tk
    ```

3. Install Java Development Kit (JDK)

    Search for available JDK version:

    ```shell
    brew search jdk
    #brew search openjdk
    ```

    Install specific JDK version:

    - Open JDK 11:

        ```shell
        brew install openjdk@11
        ```

        ```shell
        brew info openjdk@11
        ```

        If not linked, create link for installed JDK 11:

        ```shell
        sudo ln -sfn /opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-11.jdk
        ```
    
    Find the Java home:

    ```shell
    /usr/libexec/java_home -V
    ```

    Or find the Java home with specific version:

    ```shell
    /usr/libexec/java_home -v11
    ```

    Set the JAVA_HOME environment variable:

    ```shell
    JAVA_HOME=$(/usr/libexec/java_home -V)
    echo 'export JAVA_HOME="/Library/Java/JavaVirtualMachines/openjdk-11.jdk/Contents/Home"' >> ~/.zprofile
    echo 'export PATH=$PATH:$JAVA_HOME/bin' >> ~/.zprofile
    ```

4. Install [Coursier](https://get-coursier.io/) and [Scala](https://www.scala-lang.org/):

    1. Install [Coursier](https://get-coursier.io/docs/cli-installation):

        ```shell
        brew install coursier/formulas/coursier
        cs setup
        ```
    
    2. Install [Scala](https://www.scala-lang.org/):
    
        ```shell
        cs install scala:2.12.18 && cs install scalac:2.12.18
        ```

5. Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/):

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

6. Install [NodeJS](https://nodejs.org/):

    ```shell
    brew install node
    ```

7. Install [Intellij](https://www.jetbrains.com/idea/):

    ```shell
    brew install --cask intellij-idea-ce
    ```

8. Install [PyCharm](https://www.jetbrains.com/pycharm/):

    ```shell
    brew install --cask pycharm-ce
    ```

9. Install [Dbeaver](https://dbeaver.io/):

    ```shell
    brew install --cask dbeaver-community
    ```

10. Install [k3d](https://k3d.io/):

    ```shell
    brew install k3d
    ```

11. Install [kubectl](https://kubernetes.io/docs/reference/kubectl/):

    ```shell
    brew install kubectl
    ```

12. Install [Helm](https://helm.sh/):

    ```shell
    brew install helm
    ```

---

### Other installations

##### Command line based

1. Install [Rust](https://www.rust-lang.org/):

    ```shell
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
    ```

##### UI installation based

###### App Store based

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

- [Microsoft Remote Desktop](https://apps.apple.com/vn/app/microsoft-remote-desktop/id1295203466)

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

- [FileZilla](https://filezilla-project.org/download.php?platform=osx)

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)

- [VSCode](https://code.visualstudio.com/download)

- [Parallels Desktop](https://www.parallels.com/products/desktop/)

- [VMWare Fusion](https://download3.vmware.com/software/FUS-1302/VMware-Fusion-13.0.2-21581413_universal.dmg)

- [XMind 8](https://dl3.xmind.net/xmind-8-update9-macosx.dmg) with (optional) [template](https://xmind.app/blog/mind-map-presentation-template/)
