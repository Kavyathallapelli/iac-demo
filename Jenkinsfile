pipeline {
    agent any
    
    tools {
        terraform 'terraform1'
    }
    
    stages {
        stage('gitclone') {
            steps{
                git credentialsId: 'github_cred', url: 'https://github.com/sunakarasatish/iac-demo.git'
            }
        }
        
        stage('terraform init') {
            steps{
                sh label: '', script: 'terraform init'
            }
        }
        
        stage('terraform apply') {
            steps{
                sh label: '', script: 'terraform apply --auto-approve'
            }
        }
        stage('Terraform destroy') {
            steps {
                sh label: '', script: 'terraform destroy --auto-approve'
            }
        }
    }
}
