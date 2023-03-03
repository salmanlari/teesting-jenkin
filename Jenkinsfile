pipeline{
    agent any
    environment{
        DOCKERHUB_CREDENTIALS= credentials("dockerhub")
    }
    stages{
        stage ("clone git repo"){
            steps{
                
            git "https://github.com/salmanlari/docker-buil-and-push-image-using-jenkins.git"
            }
        }
        stage ("build docker image"){
            steps{
                sh "dokcer build -t 7011347758/test:v1 ."
            }
        }
        stage ("login"){
            steps{
                sh "echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin"
            }
        }
        stage ("image push on docker hub"){
            steps{
                sh "docker push 7011347758/test:v1"
            }
        }
    }
}
