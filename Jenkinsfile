pipeline {
    agent any 
    tools {
        maven 'localMaven' 
    }
    stages {
        stage('BUILD') {
            steps {
                build 'payslip'
            }
        }
        stage('TEST'){
            steps{
                build 'payslip-test'
            }
        }
        stage('DEPLOY'){
            steps{           
                build 'payslip-deploy'
            }
        }
    }
}
        
