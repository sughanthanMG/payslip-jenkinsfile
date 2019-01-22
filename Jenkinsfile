pipeline {
    agent any 
    tools {
        maven 'localMaven' 
    }
    stages {
        stage('BUILD') {
            steps {
                build 'payslip-source'
            }
        }
        stage('TEST'){
            steps{
                build 'payslip-test'
            }
        }
        stage('DEPLOY'){
            steps{
                build 'payslip-build'
                build 'payslip-deploy'
            }
        }
    }
}
        
