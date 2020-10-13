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
                
                sh 'ls -al'
                sh 'pwd'
                
                sh label: '', returnStatus: true, script: 'cppcheck --enable=all --inconclusive --xml --xml-version=2 /var/jenkins_home/workspace/Pipeline_demo@2 2> cppcheck.xml'
                /*publishCppcheck allowNoReport: true, ignoreBlankFiles: true, pattern: '/var/jenkins_home/workspace/Pipeline_demo@2/*.xml'*/
                
                sh 'ls -al'
                sh 'pwd'
                
            }
        }
    }
}
