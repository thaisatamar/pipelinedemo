pipeline {
  agent {
    kubernetes {
      yaml '''
        apiVersion: v1
        kind: Pod
        metadata:
          labels:
            some-label: some-label-value
        spec:
          containers:
          - name: maven
            image: node:alpine
            command:
            - cat
            tty: true
          - name: busybox
            image: busybox
            command:
            - cat
            tty: true
        '''
    }
  }
  stages{
            stage('build') {
                steps {
                    sh 'node --version'
                    sh 'npm install'
                }
            }
            stage('test') {
                steps {
                    sh 'npm test'
                }
            }
        }
}
    

