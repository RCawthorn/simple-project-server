pipeline {
    agent any

    stages {
        stage('Testing Environment') {
            steps {
                    sh 'mvn package -DskipTests'

                }
            }
        stage('Build') {
            steps {
		echo "Build"
                }
            }
        stage('Deploy') {
            steps {
		echo "Deploy"
            }
        }
    }
}

