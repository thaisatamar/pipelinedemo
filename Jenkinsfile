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
          - name: npm
            image: node:16.3.0-alpine
            command:
            - cat
            tty: true
        '''
    }
  }
  stages{
            stage('build') {
              container('npm'){
                steps {
                    sh 'node --version'
                    sh 'npm install'
                }
              }
            }
            stage('test') {
                steps {
                    sh 'npm test'
                }
            }
        }
}
    

