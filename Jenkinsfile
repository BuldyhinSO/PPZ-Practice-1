pipeline {
    agent any
    environment {
        PYTHON_VERSION = '3.11'
    }
    tools {
        pyenv 'pyenv'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                doGenerateSubmoduleConfigurations: false,
                extensions: [], submoduleCfg: [],
                userRemoteConfigs: [[url: 'https://github.com/BuldyhinSO/PPZ-Practice-1.git']]])
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'poetry install'
            }
        }
        stage('Test') {
            steps {
                sh 'poetry run pytest tests'
            }
        }
        stage('Lint') {
            steps {
                sh 'poetry run flake8'
            }
        }
        stage('Deploy') {
            steps {
                sh 'fab deploy'
            }
        }
    }
}
