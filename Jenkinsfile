pipeline{
    agent any
        stages{
            stage("k8s"){
                steps{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'cluster', contextName: '', credentialsId: 'kube', namespace: 'default', serverUrl: 'https://494DC0F033B24CB1F89C165EB78571E3.sk1.eu-west-2.eks.amazonaws.com']]) 
                    {
                    sh 'curl -LO "https://14499ECDF350D41D44782C65DBF3E14D.gr7.eu-west-2.eks.amazonaws.com"'
                    sh 'chmod u+x ./kubectl'
                    sh './kubectl get nodes'
                    sh './kubectl create -f pod.yaml'
                    sh './kubectl get pods'
                    }
                }    
        }
    }
}
