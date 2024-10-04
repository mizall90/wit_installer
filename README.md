## Install Bazel 1.0.0

1. Install Bazel version 1: 
please follow the instructions: https://bazel.build/install/ubuntu
                   or
a. copy all command from line no. 5 to 8 and run in terminal
sudo apt install apt-transport-https curl gnupg -y
curl -fsSL https://bazel.build/bazel-release.pub.gpg | gpg --dearmor >bazel-archive-keyring.gpg
sudo mv bazel-archive-keyring.gpg /usr/share/keyrings
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/bazel-archive-keyring.gpg] https://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list

b. Download and isntall bazel installer from: https://github.com/bazelbuild/bazel/releases 
chmod +x bazel-1.0.0-installer-linux-x86_64.sh
./bazel-1.0.0-installer-linux-x86_64.sh --user

c. Setup environment 
export PATH="$PATH:$HOME/bin"

2. Run bazel to build the html file for wit: 
a. change pwd to "what-if-tool" project
b. run command: bazel run wit_dashboard/demo:demoserver 
c. try different demos by changing "demoserver": these are available in: what-if-tool/wit_dashboard/demo/BUILD file

3. If error due to python while building please update: 
$sudo ln -s /usr/bin/python3 /usr/bin/python