node {
   
   stage('Code Checkout') { 
     git credentialsId: 'githubID', url: 'https://github.com/itrainjaquar/maven-examples.git'
     
    }
   stage('Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn clean compile'
      }
    }
   stage('Unit Test run') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn test'
      } 
    }
   stage('Sonarqube analysis'){
    withSonarQubeEnv(credentialsId: 'sonar-jaquar') {
        withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
          sh 'mvn sonar:sonar \
  
          -Dsonar.projectKey=kroy \
          -Dsonar.organization=ksingharoy1 \
          -Dsonar.host.url=https://sonarcloud.io \
          -Dsonar.login=3a61297bb51dbbb0e1ead2d7822fc8b2abba0b7a'
         
           
       }
    }
  }
  stage("Quality Gate"){
          
    }
   stage('Package to Jfrog') {
    
    }
   
   stage('Deploy to Dev') {
     
    }
   stage('Automation Testing') {
     
    }
   stage('Deploy to Test') {
     
    }
   stage('Smoke Testing') {
     
    }
   stage('Deploy to Prod') {
     
    }
   stage('Acceptance Testing') {
     
    }
}
