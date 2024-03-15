pipeline {
    agent { label 'jenkins-agent' }
    tools {
        jdk 'java1'
        maven 'maven1'
    }
    stages{
        stage("cleanup workspace"){
                  steps {
                  cleanWs()
                  }
        }

        stage("Checkout from SCM"){
                 steps {
                      git branch: 'main', credentialsid: 'github', url: 'https://github.com/somran1991/samplemaven.git'
        }

        stage("Build Application"){
                steps {
                     sh "mvn clean package"
                }
         }

        stage("Test Applicatiom"){
                steps {
                    sh "mvn test"
                }
         }
      }
}
