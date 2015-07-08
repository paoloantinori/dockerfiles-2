# Dockerfiles to run JBoss BMRS on JBoss EAP

###Download from Red Hat customer portal
http://www.jboss.org/download-manager/file/jboss-brms-6.1.0.GA-deployable.zip           
http://www.jboss.org/download-manager/file/jboss-eap-6.4.0.GA.zip

###And place them in the brms-eap folder
brms-eap/jboss-eap-6.4.0.zip    
brms-eap/business-central.war

###Build brms-eap 
docker build

###Run brms-eap 
docker run bibryam/brms-eap:latest

###Find the IP of the container (example: 172.17.0.13)
docker inspect  --format '{{ .NetworkSettings.IPAddress }}' $(docker ps -n=1 -q)

###Log into Business central with brmsAdmin and pa$word1
http://172.17.0.13:8080/business-central

###Clone git repo
git clone ssh://brmsAdmin@172.17.0.12:8001/test
