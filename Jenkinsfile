pipeline {
    agent any
    stages {
        stage('Test') {
            parallel {
              stage('Unit test') {
                steps {
                  sh './mvnw test -D testGroups=unit'
          }
        }
              stage('Integration tests') {
                  when {
                      expression { return params.RUN_INTEGRATION_TESTS }
          }
                  steps {
                      sh './mvnw test -D testGroups=integration'
          }
        }
      }    
    }
  }
}
