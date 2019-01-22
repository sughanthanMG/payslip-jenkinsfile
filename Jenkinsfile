pipeline {
    agent any 
    tools {
        maven 'apache-maven-3.6.0' 
    }
    stages {
        stage('BUILD') {
            steps {
                build 'payslip-jenkinsfile_master'
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
        
