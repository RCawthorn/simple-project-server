pipeline {
    agent any
    environment{ 
    VERSION = readMavenPom().getVersion()
    }
    

    stages {
        stage("version"){
            steps{
            echo "${VERSION}"
            }

        }
        stage('Testing') {
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
    
stage('Testing Environment') {
            steps {
                echo "hello"
            }
        }
      stage('Staging') {
           when{
                    expression{
                        env.BRANCH_NAME == 'developer'
                        
                    }
                }
            steps {
                echo "Dev"
            }
        }
      stage('Production') {
          when{
                    expression{
                        env.BRANCH_NAME == 'master'
                    }
                }
            steps {
                
                echo "production"
            }
        }
    }

}
    