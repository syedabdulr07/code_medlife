pipeline{
    agent any 
    environment {
    AWS_DEFAULT_REGION = "us-east-1"
    THE_BUTLER_SAYS_SO = credentials('ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDjpaQKJMGKZAUty1mJv51fF4Ewtz/VKpVuQrjfnOJaV00ZQ8pyGvp5NzLhqRZFwcQMwdG3XcRFw0aVq1+LnjTUBVKAFPKoQjxylRiHoEffj+ZKxjLc+fnfmrGDtkKpQ+tJiGgL4wYrBSJRgocOocPANM/nkLLvBK+KURPv1ufT3mavUWBatg+pNA1fRlffQE0ROA2q2CBfkH4xJWDwRdhVf9wg9Wf/ToqXlOuvAa0Cfq9Igkh/z6O6jNlOFli2G+Jp0/iJJ5PA6NZx0+UGkeS59EEgIeUhWUkQ3jkMvWNzv3D5jgyEquwk+xgM5dCdmb4W3Na0FK25CBPfHJ7zIazl ubuntu@ip-172-31-22-7')
    }
    stages {
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