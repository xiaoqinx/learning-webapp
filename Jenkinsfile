def builderImage
def productionImage
def ACCOUNT_REGISTRY_PREFIX
def GIT_COMMIT_HASH

pipeline {
    agent any
    stages {
        stage('Checkout Source Code and Logging Into Registry') {
            steps {
                echo 'Logging Into the Private ECR Registry'
                script {
                    GIT_COMMIT_HASH = sh (script: "git log -n 1 --pretty=format:'%H'", returnStdout: true)
                    ACCOUNT_REGISTRY_PREFIX = "581251645584.dkr.ecr.ap-southeast-2.amazonaws.com"
                    sh """
                    \$(aws ecr get-login --no-include-email --region ap-southeast-2)
                    """
                }
            }
        }
    }
}
