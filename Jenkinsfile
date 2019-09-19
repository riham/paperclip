pipeline {
    agent any

    stages {
        stage('Test development version') {
            when {
                not {
                    branch 'master'
                }
            }
            steps {
                sh 'echo "ololo"'
            }
        }
        stage('Build nightly image') {
            when {
                branch 'master'
            }
            steps {
                script {
                    sh '/bin/bash pyenv virtualenv 3.7.2 ppenv; pyenv activate "${ppenv: -1}"'
                    sh '/bin/bash python3 setup.py sdist'
                }
            }
        }
    }
}
