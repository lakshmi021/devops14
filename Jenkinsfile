pipeline{
    agent any;
    stages{
        stage("git hub cloning"){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'devops-eks-project-jenkins-id', url: 'git@github.com:lakshmi021/devops14.git']])
            }
        }
        stage("terraform init"){
            steps{
                sh 'terraform init'
            }
        }
        stage("terraform plan"){
            steps{
                sh 'terraform plan'
            }
        }
        stage("terraform apply"){
            steps{
                sh 'terraform apply --auto-approve'
            }
        }
    }
}
