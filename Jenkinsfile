pipeline{
   agent {label 'master'}
   tools{
        maven 'maven'
     }
     parameters {
  choice choices: ['build', 'sonar-scan', 'compile'], description: 'choose what action to be performed', name: 'Stage'
}
   stages {
       stage('build') {
          steps{
            sh 'mvn clean package'
            }
          }
       stage('sonar-scan') {
          steps{
          sh 'mvn install sonar:sonar -Dsonar.login=admin -Dsonar.password=1234 -Dsonar.host.url=http://35.188.201.171:8081'
           }
         }
        stage('compile') { 
          steps{
          sh 'mvn clean compile'
          }
       } 
   } 
}  
          

        
     
