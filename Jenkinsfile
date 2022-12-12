pipeline {
    agent any
    tools {
	maven 'Maven 3.8.6'
    }
    stages {
        stage('Build Step') {
            steps { 
		echo 'builing....'
		sh 'mvn --version'
                sh 'mvn -B -DskipTests clean package'
            }
        }
       	stage('Test') {
            steps {
                sh 'mvn test'
            }
       	}
 	stage('docker push') {
            steps {
                sh 'aws --version'
		sh 'docker --version'
		sh 'aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 319937213100.dkr.ecr.ap-south-1.amazonaws.com'
 		sh 'docker build -t samplejavarepositiry .'
		sh 'docker tag samplejavarepositiry:latest 319937213100.dkr.ecr.ap-south-1.amazonaws.com/samplejavarepositiry:latest'
		sh 'docker push 319937213100.dkr.ecr.ap-south-1.amazonaws.com/samplejavarepositiry:latest'
            }
       }
    }
}
