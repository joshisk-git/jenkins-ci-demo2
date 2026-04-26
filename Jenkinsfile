pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'chmod +x app.sh'
                sh './app.sh'
            }
        }

        stage('Test') {
            steps {
                sh 'chmod +x test.sh'
                sh './test.sh'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deployment done"
            }
        }

        stage('Archive') {
            when {
                branch 'main'
            }
            steps {
                archiveArtifacts artifacts: 'app.sh'
            }
        }
    }
}
