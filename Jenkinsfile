pipeline {
    agent any

    stages {

        stage('Source') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/ankita0513/jenkins_demo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building HTML application...'
                sh 'ls -l'
                sh 'test -f index.html'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing HTML application...'
                sh 'grep -qi "<html" index.html'
                echo 'HTML file check passed!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Preparing application for deployment...'
                sh 'mkdir -p /tmp/jenkins-deployment'
                sh 'cp index.html /tmp/jenkins-deployment/'
                echo 'Application copied to deployment directory.'
            }
        }
    }
}
