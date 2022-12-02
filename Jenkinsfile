pipeline {
    agent any
    stages {
        stage('Build Step') {
            steps { 
		echo 'builing....'
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
