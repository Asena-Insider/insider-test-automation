pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'screenshots/*.png', fingerprint: true
            archiveArtifacts artifacts: 'reports/*.html', fingerprint: true
        }
    }
}