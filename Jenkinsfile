pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                dir('frontend-flask') {
                    sh 'pip3 install -r requirements.txt'
                }
            }
        }

        stage('Run App') {
            steps {
                dir('frontend-flask') {
                    sh '/usr/bin/pm2 restart flask-app || /usr/bin/pm2 start app.py --name flask-app --interpreter python3'
                }
            }
        }
    }
}
