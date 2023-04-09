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
                    sh 'pip3 install -r requirements.txt'
                    sh 'python3 manage.py test'
                    sh 'flake8'
                }
            }
        }
    }

    post {
        always {
            script {
                def server = sh(script: "jps | grep 'django.core.management' | awk '{ print \${1} }'", returnStdout: true).trim()
                sh "kill $server"
            }
        }
    }

}
