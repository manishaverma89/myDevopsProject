pipeline {
  agent {
    kubernetes {
        label 'maven'
    }
  }
  stages {
    stage('Run maven') {
      steps {
        container('maven') {
          sh 'mvn -version '
          sh 'hostname'
          sh 'whoami'
          sh 'ls -lart'
          sh 'curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"'
          sh 'install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl'
          script {
          withKubeConfig(credentialsId: 'kubeconfigplain', contextName: 'minikube') {
          //sh 'kube'
          //git branch: 'main', url: 'https://github.com/manishaverma89/myDevopsProject.git'
          sh 'ls -lart'
         // sh 'kubectl apply -f nginxpod.yml -n devops-tools'
} }
        }
      }
    }
  }
}
