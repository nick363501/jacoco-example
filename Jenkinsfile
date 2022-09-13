pipeline {
    agent any
    environment {
        MVN_HOME="/opt/homebrew"
    }
    stages {
        stage ('Build') {
            steps {
                sh "${MVN_HOME}/bin/mvn clean package"
                jacoco()            }
        }
        stage ('Publish') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
    }
}