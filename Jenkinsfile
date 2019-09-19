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
                    sh 'source ~/.bashrc'
                    sh 'pyenv virtualenv --force 3.7.4 ppenv; pyenv activate ppenv'
                    sh 'python3 setup.py sdist'
                }
            }
        }
    }
}
