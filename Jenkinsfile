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
                
                sh label: '', returnStatus: true, script: 'cppcheck --enable=all --inconclusive --xml --xml-version=2 . > /tmp/cppcheck.xml'
                publishCppcheck allowNoReport: true, ignoreBlankFiles: true, pattern: '/tmp/cppcheck.xml'
                
            }
        }
    }
}
