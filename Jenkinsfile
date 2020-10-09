pipeline {
    agent any 
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'lbeschastny/jenkins-build-essential'
                }
            }
            steps {
                sh 'make'
                sh './testBin'
                cppcheck --xml --xml-version=2.2> cppcheck.xml
            }
        }
    }
}
