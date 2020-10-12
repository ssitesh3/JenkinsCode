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
                
                sh label: '', returnStatus: true, script: 'cppcheck --xml --xml-version=2 JenkinsCode 2> cppcheck.xml'
                /*sh label: '', returnStatus: true, script: 'cppcheck . --xml --JenkinsCode=main.cpp 2> cppcheck-result.xml'*/
                /*sh label: '', returnStatus: true, script: 'cppcheck . --xml --language=c++ --suppressions-list=suppressions.txt 2> cppcheck-result.xml'*/
                
                publishCppcheck allowNoReport: true, ignoreBlankFiles: true, 
                                                     pattern: '*()cppcheck-result.xml'
                
            }
        }
    }
}
