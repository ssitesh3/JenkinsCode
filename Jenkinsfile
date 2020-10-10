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
                
                sh 'cppcheck Makefile'
                /*publishCppcheck allowNoReport: true, ignoreBlankFiles: true, */
                                                     //pattern: '**/cppcheck-result.xml'
            }
        }
    }
}
