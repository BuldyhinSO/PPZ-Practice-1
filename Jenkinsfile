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
                    sh 'ls'
                    sh 'pip3 install --upgrade pip'
                    sh 'pip3 install -r requirements.txt'
                    sh 'python3 manage.py test'
                    sh 'pip3 install flake8'
                    sh '/Users/ybw0000/Library/Python/3.9/bin/flake8 .'
                }
            }
        }
    }
}
