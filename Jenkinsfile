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
                deploy("**/*.war", 'localhost', "payslip_app_$BUILD_NUMBER")
            }
        }
    }
}
        // Deploy file to tomcat
def deploy(file, host, context) {
sh "curl -v -u tomcat:tomcat -T ${file} 'http://${host}:8889/manager/text/deploy?path=${context}&update=true'"
}
