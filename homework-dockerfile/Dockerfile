# допустим
from ubuntu:20.04
run apt update
run DEBIAN_FRONTEND=noninteractive TZ=Etc/UTC apt install -y git maven wget default-jdk 
run wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.95/bin/apache-tomcat-9.0.95.tar.gz
run tar xfz ./apache-tomcat-9.0.95.tar.gz
run git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello
run cd boxfuse-sample-java-war-hello/ && mvn clean package
workdir "boxfuse-sample-java-war-hello/target"
run chmod +x hello-1.0.war
run mv hello-1.0.war /var/lib/tomcat9/webapps/

run mkdir -p /usr/share/tomcat9/conf/
run ln -s /etc/tomcat9/server.xml /usr/share/tomcat9/conf/server.xml
run ln -s /etc/tomcat9/tomcat-users.xml /usr/share/tomcat9/conf/tomcat-users.xml

run mkdir -p /usr/share/tomcat9/temp

expose 8080
cmd ["/usr/share/tomcat9/bin/catalina.sh", "run"]
