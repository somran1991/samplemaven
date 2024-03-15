pipeline {
    agent { label 'jenkins-agent' }
    tools {
        jdk 'Java11'
        maven 'maven3'
    }
    stages {
        stage("cleanup workspace") {
            steps {
                cleanWs()
            }
        }

        stage("Checkout from SCM") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/somran1991/samplemaven.git'
            }
        }

        stage("Build Application") {
            steps {
                sh "mvn clean package"
            }
        }

        stage("Test Application") {
            steps {
                sh "mvn test"
            }
        }
    }
}
