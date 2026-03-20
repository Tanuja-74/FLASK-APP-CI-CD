pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/Tanuja-74/FLASK-APP-CI-CD.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run App') {
            steps {
                sh 'pm2 restart flask-app || pm2 start app.py --name flask-app'
            }
        }
    }
}
