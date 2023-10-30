pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from a version control system (e.g., Git)
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Compile your Java application (e.g., using Maven)
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Run tests (e.g., JUnit tests)
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy your application to a server
                sh 'scp target/your-app.war user@your-server:/path/to/deployment/'
            }
        }
    }

    post {
        success {
            // This block is executed if the pipeline is successful
            echo 'Pipeline successful!'
        }
        failure {
            // This block is executed if the pipeline fails
            echo 'Pipeline failed!'
        }
    }
}pipeline {
	agent any
	tools {
	maven 'MAVEN_HOME'
	}
	stages {
		stage('Stage1: Clean Stage 1') {
			steps {
				bat 'mvn clean'
				}
			}
		stage ('Stage 2: Test Stage') {
			steps {
				bat 'mvn test'
				}
			}
		stage ('Stage 3: My Package'){
			steps {
				bat 'mvn package'
				}
			}			
		stage ('Stage 4: My Final Build Stage'){
			steps {
				bat 'mvn install'
				}
			}	
		stage ('Stage Final: Build Success'){
			steps {
				echo  'Build Success!'
				}
			}
		}
	}		
