$ sudo apt remove default-jdk default-jre openjdk-headless 

$ sudo apt install openjdk-8-jdk openjdk-8-jre 

$ java -version 
$ javac -version 

$ sudo vim ~/.bashrc (sudo apt install vim) 

export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64 
export PATH=$PATH:$JAVA_HOME (esc + :wq) 


$ source ~/.bashrc 


$ echo $PATH 
$ echo $JAVA_HOME 
$ sudo adduser hadoop 
$ sudo usermod -aG sudo hadoop 
4. Once the user is added, login to the user Hadoop to generate the ssh key for passwordless login (hadoop@machinename) 
$ sudo su - hadoop 
$ ssh-keygen -t rsa 
$ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys 
$ chmod 0600 ~/.ssh/authorized_keys 
$ ssh localhost
$ exit 

https://drive.google.com/file/d/1hgQAzqUi2HaSRdX1ZnmVXEBjI04gFYHR/view?usp=sharing
//cd ~/Downloads

$ tar -xvzf hadoop-3.1.4.tar.gz 
$ sudo mv hadoop-3.1.4 /usr/local/hadoop 
. Setup the dedicated PATH variables for Hadoop as hadoop-java.sh as follows, 

$ sudo vim /etc/profile.d/hadoop_java.sh 

export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64 
export HADOOP_HOME=/usr/local/hadoop 
export HADOOP_HDFS_HOME=$HADOOP_HOME 
export HADOOP_MAPRED_HOME=$HADOOP_HOME 
export YARN_HOME=$HADOOP_HOME 
export HADOOP_COMMON_HOME=$HADOOP_HOME 
export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native export PATH=$PATH:$JAVA_HOME/bin:$HADOOP_HOME/bin:$HADOOP_HOME/sbin export HADOOP_OPTS="$HADOOP_OPTS 
-Djava.library.path=$HADOOP_HOME/lib/native" 

$ source /etc/profile.d/hadoop_java.sh 

$ hadoop version 

$ hdfs version
