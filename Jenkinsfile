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
 	stage('docker') {
            steps {
                sh 'docker --version'
            }
       }
    }
}
