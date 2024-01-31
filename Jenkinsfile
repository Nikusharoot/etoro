pipeline {
    agent any
    stages {
        stage('Deploy Helm Chart') {
            steps {
                script {
                    // Clone your Helm chart repository
                    git url: 'https://github.com/your-username/your-helm-chart-repo.git'
                    
                    // Deploy the Helm chart
                    sh 'helm install my-app ./your-helm-chart-repo --namespace nika'
                }
            }
        }
        stage('Destroy Helm Chart') {
            steps {
                script {
                    // Delete the Helm release to destroy the chart
                    sh 'helm delete my-app --namespace nika'
                }
            }
        }
    }
}
