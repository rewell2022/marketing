pipeline {
    agent any

    stages {

        stage ('check if docker is installed') {
            steps {
                sh 'docker --version'
            }
        }
        
        stage ('build docker images') {
            steps {
                sh 'docker build .'
            }
        }
        

    }
}
