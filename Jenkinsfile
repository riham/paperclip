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
                    sh 'pyenv virtualenv paperclip; pyenv activate "${paperclip: -1}"'
                    sh 'python3 setup.py sdist'
                }
            }
        }
    }
}
