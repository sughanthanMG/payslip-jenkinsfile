pipeline {
    agent any 
    tools {
        maven 'localMaven' 
    }
    stages {
        stage('BUILD') {
            steps {
                build 
            }
        }
        stage('TEST'){
            steps{
                
                checkstyle canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: ''
            }
        }
        stage('DEPLOY'){
            steps{
                
                sh 'curl -v -u tomcat:tomcat -T "**/*.war" "http://localhost:8889/manager/text/deploy?path=payslip_app_$BUILD_NUMBER&update=true"'
}
        }
    }
}
        
