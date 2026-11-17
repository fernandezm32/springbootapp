pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/fernandezm32/springbootapp.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the fat jar'
                sh 'chmod +x mvnw'
                sh './mvnw clean package -DskipTests'
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
