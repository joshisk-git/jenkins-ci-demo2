pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-pat', url: 'https://github.com/joshisk-git/jenkins-ci-demo2.git'
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
    }

    post {
        success {
            archiveArtifacts artifacts: 'app.sh'
        }
    }
}
