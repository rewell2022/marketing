pipeline { 

    agent any

    environment {
        DOCKERHUB_CREDENTIALS= credentials('djoum1983')
    }
    
    stages {

        stage ('build the docker image') {
            steps {
                sh 'docker build -t djoum1983/marketing .'
            }
        }

        stage ('login to dockerhub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW |  docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                   echo 'login completed'
            }
        }
    
        stage ('push the image into dockerhub') {
            steps {
                sh ' docker push djoum1983/marketing'
            }
        }
    } 

    post {

        always {
            sh 'docker logout'
        }
    } 

}


