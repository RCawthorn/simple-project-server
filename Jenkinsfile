pipeline {
    agent any

    stages {
        stage('Testing Environment') {
            steps {
			sh 'mvn test -Dtest=IntegrationSuite'
				sh 'mvn test -Dtest=ControllerAndServiceSuite'
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
			sh 'docker push cawthorn/simple-project:latest'
		echo "Deploy"
            }
        }
    }
}

