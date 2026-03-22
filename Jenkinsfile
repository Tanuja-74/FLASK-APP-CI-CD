pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git credentialsId: 'github-creds', url: 'https://github.com/Tanuja-74/FLASK-APP-CI-CD.git'
            }
        }

        stage('Install') {
            steps {
                dir('frontend-flask') {
                    sh '''
                    python3 -m venv venv
                    source venv/bin/activate
                    pip install -r requirements.txt
                    '''
                }
            }
        }

        stage('Run') {
            steps {
                dir('frontend-flask') {
                    sh '''
                    pm2 restart flask-app || pm2 start app.py --name flask-app --interpreter python3
                    '''
                }
            }
        }
    }
}
