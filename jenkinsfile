pipeline {
    agent any

    environment {
        // Update PATH to include the Terraform installation directory
        PATH = "C:\\Users\\Lenovo\\Downloads\\terraform_1.10.5_windows_amd64;$PATH"
    }

    stages {
        stage('Terraform init') {
            steps {
                // Inject AWS credentials and execute terraform destroy
                withCredentials([string(credentialsId: 'aws-access-key-id', variable: 'AWS_ACCESS_KEY_ID'),
                                 string(credentialsId: 'aws-secret-access-key', variable: 'AWS_SECRET_ACCESS_KEY')]) {
                    bat 'terraform init'
                }
            }
        }
            stage('Terraform plan') {
            steps {
                // Inject AWS credentials and execute terraform destroy
                withCredentials([string(credentialsId: 'aws-access-key-id', variable: 'AWS_ACCESS_KEY_ID'),
                                 string(credentialsId: 'aws-secret-access-key', variable: 'AWS_SECRET_ACCESS_KEY')]) {
                    bat 'terraform plan'
                }
            }
        }
            stage('Terraform Apply') {
            steps {
                // Inject AWS credentials and execute terraform destroy
                withCredentials([string(credentialsId: 'aws-access-key-id', variable: 'AWS_ACCESS_KEY_ID'),
                                 string(credentialsId: 'aws-secret-access-key', variable: 'AWS_SECRET_ACCESS_KEY')]) {
                    bat 'terraform apply --auto-approve'
                }
            }
        }
            stage('Terraform Destroy') {
            steps {
                // Inject AWS credentials and execute terraform destroy
                withCredentials([string(credentialsId: 'aws-access-key-id', variable: 'AWS_ACCESS_KEY_ID'),
                                 string(credentialsId: 'aws-secret-access-key', variable: 'AWS_SECRET_ACCESS_KEY')]) {
                    bat 'terraform destroy --auto-approve'
                }
            }
        }
    }
}
