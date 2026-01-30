pipeline {
    agent { 
        label 'Jenkin-Agents' 
    }

    tools {
        jdk 'Java - 21.0.9'
        maven 'Maven3.9.12'
    }

    stages {

        stage('Cleanup Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout from SCM') {
            steps {
                git branch: 'main',
                    credentialsId: 'github',
                    url: 'https://github.com/lykienhuy/jenkintest'
            }
        }

        stage('Build Application') {
            steps {
                sh 'mvn clean package'
            }
        }

    }
}
