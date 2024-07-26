pipeline {
    agent any
    
    
    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building ...."
                    withEnv(["PATH+MAVEN=${env.MAVEN_HOME}//bin"]) {
                        sh 'mvn clean install'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo "Test..."
                    
		}
            }
        }
    }
    post {
        success {
            echo 'Build and test succeeded!'
        }
        failure {
            echo 'Build or test failed!'
        }
    }
}

