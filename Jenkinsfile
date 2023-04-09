pipeline {
    agent any

    environment {
        PATH = "/opt/homebrew/bin:${env.PATH}"
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/BuldyhinSO/PPZ-Practice-1.git'
            }
        }
        stage('Run project') {
            steps {
                dir ('todo') {
                    withPythonEnv('Python3.11') {
                        sh 'python --version'
                        sh 'pip install --upgrade pip'
                        sh 'poetry install'
                        sh 'poetry run manage.py test'
                        sh 'poetry run flake8 .'
                    }
                }
            }
        }
    }
}
