node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'githubID', url: 'https://github.com/prabhu9683/maven-examples.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn clean compile'
    }  
   }
   stage('Test Run') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
        sh 'mvn test'
     }  
   }
   stage('Code Quality') {
      sh 'mvn sonar:sonar \
         -Dsonar.projectKey=mavenex \
         -Dsonar.organization=itrainprabhu \
         -Dsonar.host.url=https://sonarcloud.io \
         -Dsonar.login=5870870dfe1749ce1b15deb7abb66ceb2622b3bd'    
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Dev') {
   } 
   stage('Deploy to Test') {
   }
   stage('Deploy to Prod'){
   }
}
