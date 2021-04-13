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
