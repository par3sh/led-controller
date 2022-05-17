pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                echo 'checking out'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '1f608af5-30c0-4c56-86fa-cc027c071008', url: 'https://github.com/par3sh/led-controller.git']]])
            }
        }
        stage('Build') {
            steps{
                git branch: 'main', credentialsId: '1f608af5-30c0-4c56-86fa-cc027c071008', url: 'https://github.com/par3sh/led-controller.git'   
                bat '''SET PATH = %path%
                main.py'''
            }
        }
        stage('Test') {
            steps{
                echo 'Testingggg'
            }
        }
    }
}
