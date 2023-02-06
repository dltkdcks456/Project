/var/lib/jenkins/workspace/rideway



/var/lib/jenkins/workspace/rideway/backend/demo-1/build/libs/*.jar

/var/lib/jenkins/workspace/rideway/backend/demo-1/build/libs/


cd /home/ubuntu/jenkins/
nohup ./build.sh > /dev/null 2>&1 &


nohup java -jar /home/ubuntu/jenkins/demo-1-0.0.1-SNAPSHOT.jar > /dev/null 2>&1 &

tail -200f log.log

rm -rf demo-1-0.0.1-SNAPSHOT.jar logs/
ps -ef | grep java

sudo kill -9 57737 57740

- 관리자 권한을 잘 지정해주어야 하고
- 파일 경로 또한 신경써서 살펴주어야 한다.







/var/lib/jenkins/workspace/rideway



/var/lib/jenkins/workspace/rideway/backend/demo-1/build/libs/*.jar

/var/lib/jenkins/workspace/rideway/backend/demo-1/build/libs/


cd /home/ubuntu/jenkins/
nohup ./build.sh > /dev/null 2>&1 &


nohup java -jar /home/ubuntu/jenkins/demo-1-0.0.1-SNAPSHOT.jar > /dev/null 2>&1 &

tail -200f log.log

rm -rf demo-1-0.0.1-SNAPSHOT.jar logs/
ps -ef | grep java

sudo kill -9 57737 57740


-=================================
echo ${WORKSPACE}

export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export PATH="$PATH:$JAVA_HOME/bin"
cd /var/lib/jenkins/workspace/rideway/backend/demo-1
chmod +x ./gradlew
./gradlew clean bootJar

===========================================

rm -rf /home/ubuntu/jenkins/demo-1-0.0.1-SNAPSHOT.jar

cp -R /var/lib/jenkins/workspace/rideway/backend/demo-1/build/libs/*.jar /home/ubuntu/jenkins/

nohup java -jar /home/ubuntu/jenkins/demo-1-0.0.1-SNAPSHOT.jar &


=====================================
cd /var/lib/jenkins/workspace/rideway/frontend

pwd

npm install --legacy-peer-deps
CI=false
npm run build

========================
/var/lib/jenkins/workspace/frontend/build/**

/var/lib/jenkins/workspace/frontend/build/

/home/ubuntu/myapp

nohup java -jar /home/ubuntu/jenkins/demo-1-0.0.1-SNAPSHOT.jar &

======================================

catalina.out
<-- 비지니스로직

access.log
<-- 서버에 접속이력 로그