pipeline {
    agent any

    stages {
        stage('Testing Environment') {
            steps {
			sh 'mvn package -DskipTests'
				sh 'docker build -t="cawthorn/simple-project:latest" .'
                }
            }
        stage('Build') {
            steps { sh 'mvn package -DskipTests'
			sh 'docker build -t="cawthorn/simple-project:latest" .'
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

