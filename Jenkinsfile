pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m pip install --upgrade pip
python3 -m pip install -r requirements.txt'
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
