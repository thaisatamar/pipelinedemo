podTemplate(yaml: '''
    apiVersion: v1
    kind: Pod
    spec:
      containers:
      - name: npm
        image: node:alpine
        command:
        - sleep
        args:
        - 99d
''') {
  node(POD_LABEL) {
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
    

