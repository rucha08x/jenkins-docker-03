pipeline {
	agent any
	environment {
		DOCKER_IMAGE_NAME='my-java-image'
	}

	stages {
		stage("checkout") {
			checkout scm
		}
		stage("build") {
			sh 'javac HelloWorld.java'
		}
		stage("build Docker image") {
			sh 'docker build -t $DOCKER_IMAGE_NAME .'
		}
	}

	post {
		success {
			echo "Build successful"
		}
		failure {
			echo "Build failed"
		}
	}
}
