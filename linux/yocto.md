## Yocto Project
    https://www.yoctoproject.org/docs/3.0/brief-yoctoprojectqs/brief-yoctoprojectqs.html

    source oe-init-build-env

    bitbake core-image-sato

## Openembedded
    http://www.openembedded.org/wiki/Getting_started

    http://layers.openembedded.org/layerindex/branch/master/layers/

## Install
    sudo apt-get install gawk wget git-core diffstat unzip texinfo gcc-multilib build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 xterm python3-subunit mesa-common-dev

    git clone git://git.yoctoproject.org/poky

## Use

    bitbake <target>

    bitbake -f -c <command> <modules>
        command: build, cleanall