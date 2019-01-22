pipeline {
    agent any 
    stages {
        stage('BUILD') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('TEST'){
            steps{
                sh 'mvn test'
                checkstyle canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: ''
            }
        }
        stage('DEPLOY'){
            steps{
                sh 'mvn clean package'
                sh 'curl -v -u tomcat:tomcat -T "**/*.war" "http://localhost:8889/manager/text/deploy?path=payslip_app_$BUILD_NUMBER&update=true"'
}
        }
    }
}
        
