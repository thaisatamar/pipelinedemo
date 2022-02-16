pipeline {
    node('node'){
        stages {
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
}
