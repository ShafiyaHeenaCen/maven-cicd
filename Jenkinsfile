pipeline{
    agent any

    tools {
         maven 'maven'
         jdk 'java'
    }

    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/ShafiyaHeenaCen/maven-cicd.git']]])
            }
        }
        stage('build'){
            steps
			
               sh 'mvn package'
            }
        }
    }
}
