pipeline {
    agent {
        docker {
            image 'composer:latest'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Checkout SCM') {
            steps {
                git 'https://github.com/22013190/phpunit-test.git'
            }
        }
        stage('Build') {
            steps {
                sh 'composer install'
            }
        }
        stage('Test') {
            steps {
                sh './vendor/bin/phpunit tests'
            }
        }
    }
}
