pipeline {
    agent any

    environment {
        KUBECONFIG = '/root/.kube/config' // Define la ubicación del archivo kubeconfig
    }

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                sh "kubectl apply -f deployment-service.yml"
            }
        }
        
        stage('Verify Deployment') {
            steps {
                sh "kubectl get svc -n webapps"
            }
        }
    }
}
