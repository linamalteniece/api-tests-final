pipeline{
    agent any
    triggers {
        pollSCM('*/1 * * * *')
    }
    stages{
        stage('build-docker-image') {
            steps {
                build_docker_image()
            }
        }
    }
}


def build_docker_image(){
    echo "Building a Docker Image from api-tests-final repository."
    sh "docker build -t lynnmal/api-tests:latest ."

    echo "Pushing image to a docker registry."
    sh "docker push lynnmal/api-tests:latest"
}