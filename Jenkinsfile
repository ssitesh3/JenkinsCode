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
                publishCppcheck allowNoReport: false, ignoreBlankFiles: true, 
                                                     pattern: '**/cppcheck-result.xml'
            }
        }
    }
}
