# допустим
from ubuntu:20.04
run apt update
run apt install -y tomcat9
run DEBIAN_FRONTEND=noninteractive TZ=Etc/UTC apt install -y git maven wget default-jdk 
run git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello
run cd boxfuse-sample-java-war-hello/ && mvn clean package
workdir "boxfuse-sample-java-war-hello/target"
run chmod +x hello-1.0.war
run mv hello-1.0.war /var/lib/tomcat9/webapps/
#run find / -name "server.xml"
run mkdir -p /usr/share/tomcat9/conf/
run ln -s /etc/tomcat9/server.xml /usr/share/tomcat9/conf/server.xml
run ln -s /etc/tomcat9/tomcat-users.xml /usr/share/tomcat9/conf/tomcat-users.xml
#run git clone https://github.com/jenkinsci/jenkins && cd jenkins/
expose 8888
cmd ["/usr/share/tomcat9/bin/catalina.sh", "run"]
