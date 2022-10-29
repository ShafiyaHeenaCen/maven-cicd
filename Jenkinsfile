pipeline{

    agent any

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
                    echo $JAVA_HOME
                    sh 'mvn clean package'
                }
            }
            
            }
        }
}
