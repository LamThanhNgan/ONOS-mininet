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

cd $ONOS_ROOT

bazel-3.0.0 build onos

bazel run onos-local clean debug

mo teerminal khac

./tools/test/bin/onos localhost

app activate org.onosproject.openflow

app activate org.onosproject.fwd

mo terminal khac

sudo mn --controller remote,ip=127.0.0.1 --custom script.py  --topo tp

https://ernie55ernie.github.io/sdn/2020/07/21/setting-up-onos-controller-with-mininet.html

https://gerrit.onosproject.org/plugins/gitiles/onos


