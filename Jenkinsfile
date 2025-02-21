pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                script {
                    // Clone the repository from GitHub
                    git branch: 'main', url: 'https://github.com/KyathamRohith/simple.git'
                }
            }
        }
        
        stage('Build') {
            steps {
                script {
                    // Clean and package the application using Maven
                    sh 'mvn clean package'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Run tests on the application
                    sh 'mvn test'
                }
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                script {
                    // Copy the .war file to the Tomcat webapps directory
                    sh 'scp target/*.war user@server:/var/lib/tomcat/webapps/'
                }
            }
        }
    }
}
