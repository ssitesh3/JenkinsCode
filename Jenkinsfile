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
                
                sh 'cppcheck --enable=all --inconclusive --xml --xml-version=2 SOURCE_DIRECTORY 2> cppcheck.xml'
                /*sh label: '', returnStatus: true, script: 'cppcheck --enable=all --inconclusive --xml --xml-version=2 JenkinsCode 2> cppcheck.xml'*/
                
                /*publishCppcheck allowNoReport: true, ignoreBlankFiles: true, pattern: '*()cppcheck.xml'*/
                
            }
        }
    }
}
