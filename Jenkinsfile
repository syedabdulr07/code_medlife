pipeline{
    agent any 
    // environment {
    // AWS_DEFAULT_REGION = "us-east-2"
    // }
    stages {
        stage ('checkout'){
            steps {
                script {
                    git branch:"{master}",
                        credentials url ('https://github.com/syedabdulr07/code_medlife.git')           
                }
            }
        }

        stage ('Deploy to S3'){ 
            steps{ 
                echo "Deploying" 
                sh "aws s3 ls" 
                sh "pwd"  
                sh "aws s3 cp ./index.html s3://maskan-bucket1"
            } 
        }

    }