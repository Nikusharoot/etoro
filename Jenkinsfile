pipeline {
    agent any
    stages {
        stage('Deploy Helm Chart') {
            steps {
                script {
                    // Clone your Helm chart repository
                    git url: 'https://github.com/Nikusharoot/your-helm-chart-repo.git'
                    
                    // Deploy the Helm chart
                    sh 'helm install my-app ./your-helm-chart-repo -n nika'

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
