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
      container('npm'){
          state('git'){
            git url 'https://github.com/thaisatamar/nodeapp.git'
          }
          stage('build') {
                    sh 'node --version'
                    sh 'npm install'
          }
         stage('test') {
      
                    sh 'npm test'
         }
            
      }
          
  }
}
    

