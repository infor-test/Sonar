pipeline{
    agent any
    /*environment {
        PATH = "$PATH:C:\Users\kisho\OneDrive\Desktop\mavenins\apache-maven-3.8.6\bin"
    }*/
    stages{
       stage('GetCode'){
            steps{
                git 'https://github.com/ravdy/sonar-project.git'
            }
         }        
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
        steps{
        withSonarQubeEnv('sonarqube-8.9.2') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar"
    }
        }
        }
       
    }
}
