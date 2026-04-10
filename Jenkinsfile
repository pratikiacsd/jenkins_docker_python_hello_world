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
	    steps {
		   script {
			if (fileExists('Dockerfile')) {
			    sh "docker build -t ${env.DOCKER_IMAGE} ."
			} else {
			    error "Dockerfile not found in the workspaces. Please create one for your python app
lication."

			}
		  }
	    }
     }

	stage('Docker Run (Optional)') {
		steps {
			sh "docker run --rm ${env.DOCKER_IMAGE}"
			}  
		}

    }


	post { 
		success { echo 'success' }
		failure { echo 'Failure' } 

		}

}

