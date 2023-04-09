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
//         stage('Run project') {
//             steps{
//                 dir ('todo'){
//                     sh 'ls'
//                     sh 'pip3 install --upgrade pip'
//                     sh 'pip3 install -r requirements.txt'
//                     sh 'python3 manage.py test'
//                     sh 'pip3 install flake8'
//                     sh '/Users/ybw0000/Library/Python/3.9/bin/flake8 .'
//                 }
//             }
//         }
            stage('Run project') {
            steps{
                dir ('todo'){
                    withPythonEnv('Python3.11'){
                        sh 'ls'
                        sh 'pip3 install --upgrade pip'
                        sh 'curl -sSL https://install.python-poetry.org | python3.11 -'
                        sh 'poetry env use 3.11'
                        sh 'poetry install && poetry shell'
                    }
                }
            }
        }
    }
}
