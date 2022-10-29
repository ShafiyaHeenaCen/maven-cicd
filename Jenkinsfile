
pipeline{

    agent any
    
       environment {
       def JAVA_HOME = '/Library/Java/JavaVirtualMachines/jdk-11.0.14.jdk/Contents/Home'                               //can be used in whole pipeline
   }

    tools {
         maven 'maven3.86'
         jdk 'jdk11'
    }

    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/ShafiyaHeenaCen/maven-cicd.git']]])
            }
        }
        stage('build'){
            steps{

                script {
                    echo JAVA_HOME
                    sh 'mvn clean package'
                }
            }
            
            }
        }
}
