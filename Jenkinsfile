pipeline {
    agent any

    tools {
        maven 'maven 3.8.4' // Ensures Jenkins manages the maven version
    }

    stages {
        stage('Initialize') {
            steps {
                echo 'Starting Velocity API Build...'
                sh 'mvn --version'
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling Java Code...'
                sh 'mvn clean compile'
            }
        }
    }
}

