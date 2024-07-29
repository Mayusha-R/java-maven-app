pipeline {
    agent any
    
    environment {
        MAVEN_HOME = tool 'Maven-3.9.0'
    }
    
    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building ...."
                    withEnv(["PATH+MAVEN=${MAVEN_HOME}//bin"]) {
                        sh 'mvn clean install'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo "Executing java file"
                    sh "java src/main/java/com/example/App.java"
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

