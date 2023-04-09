pipeline {
    agent any

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
            steps{
                dir ('todo'){
                    withPythonEnv('Python3.11'){
                        sh 'ls'
                        sh 'python --version'
                        sh 'pip install --upgrade pip'
                        sh 'curl -sSL https://install.python-poetry.org | python -'
                        sh 'poetry install && poetry shell'
                    }
                }
            }
        }
    }
}
