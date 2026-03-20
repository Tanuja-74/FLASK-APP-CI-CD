pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r frontend-flask/requirements.txt'
            }
        }

        stage('Run App') {
            steps {
                sh 'pm2 restart flask-app || pm2 start frontend-flask/app.py --name flask-app'
            }
        }
    }
}
