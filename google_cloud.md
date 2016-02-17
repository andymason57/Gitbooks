
# 


## Download Google cloud SDK: 
https://cloud.google.com/sdk/

Use 3 X f1-micro server instances to test = 10$ per hour


## Install Oracle Java 8

Installing Java 8

wget --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u65-b17/jdk-8u65-linux-x64.tar.gz

sudo mkdir /opt/jdk

sudo tar -zxf jdk-8u65-linux-x64.tar.gz -C /opt/jdk/

rm jdk-8u65-linux-x64.tar.gz

Then update-alternative:

sudo update-alternatives --install /usr/bin/java java /opt/jdk/jdk1.8.0_65/bin/java 1
sudo update-alternatives --install /usr/bin/javac javac /opt/jdk/jdk1.8.0_65/bin/javac 1

Select the number corresponding to the /opt/jdk/jdk1.8.0_65/bin/java folder from above:

sudo update-alternatives --config java
sudo update-alternatives --config javac

Finally, verify the new version is installed:

java -version

###Set up JAVA_HOME


export JAVA_HOME = /opt/jdk/jdk1.8.0_65/bin/java
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
export JAVA_HOME




## Google compute commands 

### Create an instance:

gcloud compute instances create node1 node2 node3 --custom-cpu 2 --custom-memory 8 --description firstTrialSetup --image ubuntu-14-04 --zone europe-west1-d 

### Delete an instance: 

gcloud compute instances delete


### connect to an instance:
gcloud compute ssh server_name --zone zone_name

### Copy files from local to remote: 

To copy the local file "file-1" to "my-instance" in the "us-central1-a" zone, you can use:

gcloud compute copy-files ~/file-1 my-instance:~/remote-destination --zone us-central1-a