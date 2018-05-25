pipeline {
    agent { docker { label 'docker'; image 'python:3.6' } }
    stages { 
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Build') { 
            steps {
                echo "${env.PASS}"
                sh 'python3 -m venv venv'
                sh 'pip install -U pip'
                sh 'pip install "mkdocs>=0.17.1,<0.18.0"'
                sh "mkdocs gh-deploy --remote-name https://srikanth2042:${env.PASS}/github.com/srikanth2042/my-docs.git --clean"
            }
        } 
    }
}
