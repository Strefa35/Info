# Yocto

## Yocto Project

Reference: <https://www.yoctoproject.org/docs/3.0/brief-yoctoprojectqs/brief-yoctoprojectqs.html>

```bash
source oe-init-build-env
bitbake core-image-sato
```

## OpenEmbedded

- <http://www.openembedded.org/wiki/Getting_started>
- <http://layers.openembedded.org/layerindex/branch/master/layers/>

## Install dependencies

```bash
sudo apt-get install \
  gawk wget git-core diffstat unzip texinfo gcc-multilib \
  build-essential chrpath socat cpio python3 python3-pip \
  python3-pexpect xz-utils debianutils iputils-ping python3-git \
  python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 xterm \
  python3-subunit mesa-common-dev

git clone git://git.yoctoproject.org/poky
```

## Build

```bash
bitbake <target>

# With specific command
bitbake -f -c <command> <modules>
# commands: build, cleanall
```
