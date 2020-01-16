pipeline {
  agent {
    kubernetes {
     podTemplate {
    node(Jenkins-slave) {
        stage('Run shell') {
            sh 'echo hello world'
        }
    }
}
}
