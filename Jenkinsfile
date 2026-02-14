pipeline{
    agent any

    stages {
        stage('source code') {
            steps {
                echo 'Cloning...'
                git branch: 'main', url: 'https://github.com/TEJASWINI-121/day6.git'
            }
        }

        stage('terraform') {
            steps {
                echo 'Deploying...'
                sh 'terraform init'
                sh 'terraform plan -var="ami_id=ami-0b6c6ebed2801a5cb"'
                sh 'terraform apply -var="ami_id=ami-0b6c6ebed2801a5cb" -auto-approve'
            }
        }
    }
}
