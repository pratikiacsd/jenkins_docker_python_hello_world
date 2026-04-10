// Jenkinsfile
pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'hello-world-python:latest'  // Docker image name
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/pratikiacsd/jenkins_docker_python_hello_world.git'
            }
        }

        stage('Docker Build') {
            steps {
                script {
                    if (fileExists('Dockerfile')) {
                        sh "docker build -t ${DOCKER_IMAGE} ."
                    } else {
                        error "Dockerfile not found in the workspace. Please create one for your Python application."
                    }
                }
            }
        }

        stage('Docker Run (Optional)') {
            steps {
                sh "docker run --rm ${DOCKER_IMAGE}"
            }
        }
    }
	post { 
		success { echo 'success' }
		failure { echo 'Failure' } 

	}
}
