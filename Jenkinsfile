pipeline{
    agent any 
    environment {
    AWS_DEFAULT_REGION = "us-east-2"
    }
    stages {
        stage ('checkout'){
            steps {
                script {
                    git branch:"${master}",
                        credentialsId: "${git_credential}",
                        url: "https://github.com/syedabdulr07/code_medlife.git"
                    commitId = sh (script: 'git rev-parse --short HEAD ${GIT_COMMIT}', returnStdout: true).trim()           
                }
            }
        }
        stage ('Build'){
            steps {
                echo "Building stage"
            }
        }
        stage ('Test'){
            steps {
                echo "Testing stage"

            }
        }
        stage ('Deploy to S3'){ 
            steps{ 
                echo "Deploying" 
                sh "aws configure set region us-east-2" 
                sh "aws configure set aws_access_key_id AKIAYB2ZEDMKOH7IPA45"  
                sh "aws configure set aws_secret_access_key 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"
                sh ' aws s3 cp ./index.html s3://maskan-bucket1 '
            } 
        }

    }

    post{
        success {
            echo "success"
        }
        failure {
            echo "failure"
        }
    }
}