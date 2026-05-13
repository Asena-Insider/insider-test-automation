pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
<<<<<<< HEAD
git push origin main                sh '''
                python3 -m pip install --upgrade pip
                python3 -m pip install -r requirements.txt
                '''
            }
        }

        stage('Create Folders') {
            steps {
                sh '''
                mkdir -p reports
                mkdir -p screenshots
                '''
=======
                sh 'pip install -r requirements.txt'
>>>>>>> e6c5d44635db5eee3d7737b545c414bc58b98114
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                python3 -m pytest tests/ \
                --html=reports/report.html \
                --self-contained-html
                '''
            }
        }
    }

    post {
        always {

            archiveArtifacts artifacts: 'reports/*.html', fingerprint: true

            archiveArtifacts artifacts: 'screenshots/*.png', fingerprint: true

        }
    }
}