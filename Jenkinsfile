pipeline {
    agent any

    environment {
        PATH = "/opt/homebrew/bin/poetry"
    }

    stages {
        stage('Build') {
            steps {
                sh 'python3 -c "print(\'Hello World\')"'
            }
        }
        stage('Clone'){
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
                        sh 'poetry shell'
                    }
                }
            }
        }
    }
}
