pipeline {
  agent {
    kubernetes {
      yaml """
apiVersion: batch/v1 
kind: Job 
metadata:  
  name: generate-docker-deployment 
spec:  
  template:  
    metadata:  
      labels:  
        app: generate-docker-app 
    spec:  
      terminationGracePeriodSeconds: 10  
      containers: 
        - name: my-container 
          image: 617584875936.dkr.ecr.us-east-1.amazonaws.com/cobis/docker-generator:1.1.0-ubuntu18.4 
          command: ["/bin/sh"] 
"""
    }
  }
  stages {
    stage('Run maven') {
      steps {
        container(' my-container') {
          sh 'mvn -version'
        }
      }
    }
  }
}