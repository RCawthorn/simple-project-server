pipeline {
    agent any

    stages {
        stage('Testing Environment') {
            steps {
                    sh 'mvv package -DskipTests'

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

