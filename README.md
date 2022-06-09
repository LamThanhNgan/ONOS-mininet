# ONOS-mininet
ONOS is built with Bazel
Ubuntu 18.04.6 LTS

<code>sudo ufw disable</code>

Get bridge-utils for LinuxBridge: <code>sudo apt-get install bridge-utils</code>

Installing Bazel on Ubuntu: <code>sudo apt install curl gnupg</code>

<code>curl https://bazel.build/bazel-release.pub.gpg | sudo apt-key add -</code>

echo "deb [arch=amd64] https://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list


sudo apt-get update && sudo apt-get install bazel-3.0.0

sudo apt-get install openjdk-11-jdk

sudo update-alternatives --config java

export JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64/"

sudo update-alternatives --config java


sudo update-alternatives --config javac

### Build ONOS from source

git clone https://gerrit.onosproject.org/onos

cd onos

cat << EOF > ~/.bash_profile

export ONOS_ROOT="`pwd`"

source $ONOS_ROOT/tools/dev/bash_profile

EOF

. ~/.bash_profile


