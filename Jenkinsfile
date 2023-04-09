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
                git pull 'https://github.com/BuldyhinSO/PPZ-Practice-1.git'
            }
        }
        stage('Run project') {
            steps{
                sh 'cd PPZ-Practice-1/todo/'
                sh 'ls'
                sh 'pip3 install -r requirements.txt'
            }
        }
    }
}
