pipeline {
    agent any 
    stages {
        stage('BUILD') {
            steps {
                build 'payslip-source'
            }
        }
        stage('TEST'){
            steps{
                checkstyle canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: ''
            }
        }
        stage('DEPLOY'){
            steps{
                sh 'mvn clean package'
                            }
        }
    }
}
        
