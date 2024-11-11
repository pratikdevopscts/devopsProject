pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the project'
                    bat 'mvn clean package'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo 'Testing the project'
                    bat 'mvn test'
                }
            }
        }
       
        stage('Server') {
            steps {
                script {
                    echo 'Running the project'
                    // Using 'start' to run it in the background
                    bat 'start mvn tomcat7:run'
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline finished!'
        }
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
