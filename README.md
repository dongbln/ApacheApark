# Apache Spark
This page introduces you how to install Apache Apark to do  big data tasks e.g., data scientist and data engineering tasks without installing Apache Hadoop.
## Apache Spark Installation
If you want to install Ubuntu using Vagrant use this command: <br>
`vagrant init ubuntu/trusty64; vagrant up --provider virtualbox`
### Install Java
- `sudo apt-add-repository ppa:webupd8team/java`
- `sudo apt-get update`
- `sudo apt-get install oracle-java8-installer`

### Install Scala
- `wget http://downloads.typesafe.com/scala/2.11.7/scala-2.11.7.tgz`
- `sudo mkdir /usr/local/src/scala`
- `sudo tar -xvf scala-2.11.7.tgz -C /usr/local/src/scala/`
- Edit `.bashrc`
  - `export SCALA_HOME = /usr/local/src/scala/scala-2.11.7`
  - `export PATH=$SCALA_HOME/bin:$PATH`
  - `. .bashrc`
  
- Check the installtion using `scala -version`

### Install Git
- `sudo apt-get install git`
- Test the installation using `git --version`

### Build Spark
- Download the latest version of Apache Spark
- `wget http://www.eu.apache.org/dist/spark/spark-1.5.0/spark-1.5.0.tgz`
- `tar -xvf spark-1.5.0.tgz`
- `cd spark-1.5.0/`
- `sbt/sbt assembly`
- If you got an error e.g., `failed; error='Cannot allocate memory' (errno=12)`, you must increase the main memory of your VM. The installation will take a while e.g.,  my VM required 1862 seconds to finish the build process.
- Run `bin/spark-shell` in the Spark folder to test the build process of Apache Spark
- To exist the Spark shell type `:q`in the console
