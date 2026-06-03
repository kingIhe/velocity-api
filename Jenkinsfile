pipeline {
    agent any

    tools {
        maven 'Maven 3.8.4' // Ensures Jenkins manages the maven version
    }

    stages {
        stage('Initialize') {
            steps {
                echo 'Starting Velocity API Build...'                sh 'mvn --version'
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
stage('Package') {
    steps {
        spipeline {
    agent any
    tools {
        maven 'Maven 3.8.4'
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
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            echo 'Build Successful - Artifact Archived!'
        }
    }
}
