pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'python3 -c "print(\'Hello World\')"'
            }
        }
        stage('Run project') {
            steps{
                sh 'cd todo'
                sh 'pip3 install -r requirements.txt'
            }
        }
    }
}
