pipeline{
    agent any
    triggers {
        pollSCM('*/1 * * * *')
    }
    stages{
        // stage('checkout-repo') {
        //     steps {
        //         checkout_api_tests_repo()
        //     }
        // }    
    
    stage('build-docker-image') {
            steps {
                build_docker_image()
            }
        }
    }
}

// def checkout_api_tests_repo(){
//     echo "Checking out code from api-tests-final repository."
//     git 'https://github.com/linamalteniece/api-tests-final.git'

// }

def build_docker_image(){
    echo "Building a Docker Image from api-tests-final repository."
    sh "docker build -t lynnmal/api-tests:latest ."

    echo "Pushing image to a docker registry."
    sh "docker push lynnmal/api-tests:latest"
}