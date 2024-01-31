pipeline {
    agent any
    environment {
        // Define environment variables if needed
    }
    stages {
        stage('Checkout Code') {
            steps {
                // Clone your Helm chart repository
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Nikusharoot/your-helm-chart-repo.git']]])

                // Print current directory for debugging
                sh 'pwd'
            }
        }
        stage('Deploy Helm Chart') {
            steps {
                script {
                    // Deploy the Helm chart
                    sh 'helm install my-app /home/azureuser/your-helm-chart-repo -n nika'
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
    post {
        success {
            // Perform actions on success if needed
        }
        failure {
            // Perform actions on failure if needed
        }
    }
}
