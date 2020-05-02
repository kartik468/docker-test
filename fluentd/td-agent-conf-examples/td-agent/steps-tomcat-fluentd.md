
## fluentd

- go to '/etc/td-agent'
- update td-agent.conf file to your needs
- start fluentd
  - $ sudo /etc/init.d/td-agent start


## start tomcat

- $ bin/startup.sh; tail -f logs/catalina.out

http://localhost:8080/angular8-springboot-client/employees


### spring build war
mvn clean install -DskipTests 

rm -rf /opt/tomcat/latest/webapps/springboot2-jpa-crud-example-0.0.1-SNAPSHOT.war
rm -rf /opt/tomcat/latest/webapps/springboot2-jpa-crud-example-0.0.1-SNAPSHOT

cp -r /home/ubuntu/Desktop/kartik/GIT/spring-boot-mysql-crud-angular/springboot2-jpa-crud-example/target/springboot2-jpa-crud-example-0.0.1-SNAPSHOT.war /opt/tomcat/latest/webapps/

### UI
npm run build

rm -rf /opt/tomcat/latest/webapps/angular8-springboot-client

cp -r /home/ubuntu/Desktop/kartik/GIT/spring-boot-mysql-crud-angular/angular8-springboot-client/dist/angular8-springboot-client/ /opt/tomcat/latest/webapps/


## start mongodb

- sudo systemctl start mongod
- sudo systemctl status mongod

- create mongodb database
  - use apache-logs


Status

$ sudo /etc/init.d/td-agent start

$ sudo /etc/init.d/td-agent stop

$ sudo /etc/init.d/td-agent restart

$ sudo /etc/init.d/td-agent status


see fluentd log

tail -f /var/log/td-agent/td-agent.log 


## prometheus link
http://localhost:9090

## tomcat spring boot metrics
http://localhost:8080/springboot2-jpa-crud-example-0.0.1-SNAPSHOT/actuator/prometheus
http://localhost:8080/springboot2-jpa-crud-example-0.0.1-SNAPSHOT/actuator


## fluentd metrics
http://localhost:24231/metrics

### fluentd path

Status
$ sudo /etc/init.d/td-agent start
$ sudo /etc/init.d/td-agent stop
$ sudo /etc/init.d/td-agent restart
$ sudo /etc/init.d/td-agent status

see fluentd log
 tail -f /var/log/td-agent/td-agent.log 