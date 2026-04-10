// Jenkinsfile

pipeline {
    agent any
    

    environment {
	DOCKER_IMAGE = 'hello-world-python:latest'  //Docker image name
    }


    stages {
	stage('checkout') {
	    steps {
		git branch: 'main', url:
		'https://github.com/pratikiacsd/jenkins_docker_python_hello_world.git'
		
	    }
	}


	stage('Docker Build') {
	    step {
	       script {
		   script {
			if (fileExists('Dockerfile')) {
			    sh "docker build -t ${env.DOCKER_IMAGE}."
			} else {
			    erro "Dockerfile not found in the workspaces. Please create one for your python app
lication."

			}
		}


	}


}

	stage('Docker Run (Optional)') {
		steps {
			sh "docker run --rm ${ennv.DOCKER_IMAGE}"
			}  
		}

}


	post { 
		success { echo 'success' }
		failure { echo 'Failure' } 

		}

}

