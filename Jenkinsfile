pipeline {
    agent any
    
    environment{
    	APP_PATH = /src/main/java/com/example/
    }
    
    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building ...."
                    withMaven(maven: 'Maven-3.9.0') {
                        sh 'mvn clean install'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo "Test..."
                    sh 'javac ${APP_PATH}App.java'
                    sh 'java ${APP_PATH}App'
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

