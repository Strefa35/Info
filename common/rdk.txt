## Sites
https://wiki.rdkcentral.com
https://code.rdkcentral.com

## Getting Started with the Code
https://wiki.rdkcentral.com/pages/viewpage.action?spaceKey=CMF&title=Getting+Started+with+the+Code

## Download and Build Documentation
https://wiki.rdkcentral.com/display/RDK/Download+and+Build+Documentation


## Step by step

git config --global user.name "nn nn"
git config --global user.email nn@nn.net
git config --global review."https://code.rdkcentral.com/r/".username user

echo "machine code.rdkcentral.com" >> ~/.netrc
echo "login user" >> ~/.netrc
echo "password pass" >> ~/.netrc

mkdir ~/bin
export PATH=$PATH:~/bin

curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo



