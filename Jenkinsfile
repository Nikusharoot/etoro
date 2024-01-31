pipeline {
    agent any
    stages {
 stage('Deploy Helm Chart') {
    steps {
        script {
            // Set the path to the kubeconfig file
            def kubeconfigPath = '/home/azureuser/kubeconfig.yaml'

            // Load the kubeconfig file using kubectl
            sh "kubectl --kubeconfig=${kubeconfigPath} config view"
            
            // Deploy the Helm chart
            sh "helm install my-app /home/azureuser/your-helm-chart-repo --namespace nika"
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
