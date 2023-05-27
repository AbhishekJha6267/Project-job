Pipeline{
   agent any
   environment{
      PATH = "$PATH:/opt/apache-maven-3.6.3/bin"
   }
   stages{
      stage('GetCode'){
         steps{
            git 'https://github.com/AbhishekJha6267/Project-job.git'
         }
      }
      stage('Build'){
         steps{
            sh 'mvn clean package'
         }
      }
      stage('SonarQube Analysis'){
         steps{
            withSonarQubeEnv('Sonar-Server-7.8'){
               sh "mvn sonar:sonar"
            }
         }
      }
   }
}
