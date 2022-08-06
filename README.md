									Create Web Project
									==================

# Configuration(Tomcat to Maven):-
--------------------------------
sudo su
apt update
sudo apt install -y default-jdk && sudo apt install -y maven
sudo apt install -y tomcat8 tomcat8-admin

ls /usr/lib/jvm/java-11-openjdk-amd64
ls /usr/share/maven

# Setting Path in Ubuntu16.04/18.04/20.04/21.04/22.04:-
-----------------------------------------------------
nano /home/ubuntu/.bashrc
## Start: Java,Maven,Tomcat Path Settings
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export MAVEN_PATH=/usr/share/maven
export PATH=${PATH}:${JAVA_HOME}/bin
## End: Java,Maven,Tomcat Path Settings
	
source /home/ubuntu/.bashrc

java --version && mvn --version


git clone https://github.com/NubeEra-Samples/spring-java-war.git swe
cd sparkjava-war-example/
ls -ltr
mvn package

sudo cp target/sparkjava-hello-world-1.0.war /var/lib/tomcat8/webapps/
ls /var/lib/tomcat8/webapps/

curl http://PublicIP:8080/sparkjava-hello-world-1.0/hello
nano src/main/java/HelloWorld.java
	Update Values and Save, Exit
mvn clean
mvn package
