node { 
stage 'git checkout'
git 'https://github.com/sivarasan777/DevOps-Training.git' 

stage 'Sonar Analysis'
sh 'mvn sonar:sonar -Dsonar.projectKey=sivarasan777_DevOps-Training -Dsonar.organization=sivarasan777 -Dsonar.host.url=https://sonarcloud.io'

stage 'compile'
sh 'mvn compile' 

stage 'test'
sh 'mvn test'

stage 'package'
sh 'mvn package' 

stage 'archive'
archiveArtifacts 'target/*.war'  
}
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
 node { 
stage 'git checkout'
git 'https://github.com/sivarasan777/DevOps-Training.git' 

stage 'Sonar Analysis'
sh 'mvn sonar:sonar -Dsonar.projectKey=sivarasan777_DevOps-Training -Dsonar.organization=sivarasan777 -Dsonar.host.url=https://sonarcloud.io'

stage 'compile'
sh 'mvn compile' 

stage 'test'
sh 'mvn test'

stage 'package'
sh 'mvn package' 

stage 'archive'
archiveArtifacts 'target/*.war'  
stage 'Uploading to Nexus'
sh 'curl -v -u admin:admin123 --upload-file target/*.war  http://100.25.41.202:8081/nexus/content/repositories/snapshots/'
}

node ("webserver"){  
stage ('Download *.wat to nexus') 
sh 'curl -O http://http://100.25.41.202:8081/nexus/content/repositories/snapshots/DevOps-Training.war'  
input 'Pipleline has paused and needs your input before proceeding'  

stage 'deploy war on webserver node' 
sh 'sudo cp DevOps-Training.war /var/lib/tomcat9/webapps/'  

} 
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
