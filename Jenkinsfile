pipeline {
    agent any 
    stages {
        stage{agent {docker {image 'lbeschastny/jenkins-build-essential'}}}
        stage('Build') {sh 'make' sh './testBin'}
        stage('Test') {steps {sh cppcheck JenkinsCode}}
    }
}
