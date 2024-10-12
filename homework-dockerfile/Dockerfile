# допустим
from ubuntu:20.04
run apt update
run DEBIAN_FRONTEND=noninteractive TZ=Etc/UTC apt install -y git maven wget default-jdk 
run wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.96/bin/apache-tomcat-9.0.96.tar.gz
run tar xfz ./apache-tomcat-9.0.96.tar.gz
run mv apache-tomcat-9.0.96 /var/lib/tomcat9
run git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
run cd boxfuse-sample-java-war-hello/ && mvn clean package
workdir "boxfuse-sample-java-war-hello"
run mvn package && cp target/*.war /var/lib/tomcat9/webapps/

expose 8080
cmd ["/var/lib/tomcat9/bin/catalina.sh", "run"]
