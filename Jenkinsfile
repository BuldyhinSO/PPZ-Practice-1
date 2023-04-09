pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                doGenerateSubmoduleConfigurations: false,
                extensions: [], submoduleCfg: [],
                userRemoteConfigs: [[url: 'https://github.com/BuldyhinSO/PPZ-Practice-1.git']]])
            }
        }
        stage ('Run'){
            agent{
                docker {
                    image = 'python:3.11-slim-buster'
                }
            }
            steps {
                sh 'cd todo'
                sh 'pip install -r requirements.txt'
                sh 'python manage.py runserver 0.0.0.0:8000'
            }
        }
        stage('Deploy') {
            steps {
                sh 'fab deploy'
            }
        }
    }
}
