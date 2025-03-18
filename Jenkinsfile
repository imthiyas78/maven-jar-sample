pipeline {
    agent any

    tools {
        jdk 'jdk17'          // Name of the JDK configuration in Jenkins
        maven 'maven3.9.9'    // Name of the Maven configuration in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-repo.git' // Replace with your repo URL
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package' // Build the project using Maven
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true // Archive the generated JAR file
            }
        }
    }

    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
