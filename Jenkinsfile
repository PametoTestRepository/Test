pipeline {
  agent any 
  parameters {
    choice (name: 'VERSION', choices: ['1.2.0' , '1.3.0', '1.4.0'] , description: 'just a test ')
    booleanParam(name: 'executeTests', defaultValue: true , description: 'another test')
  }
  stages {
    stage ('Build') {
      steps {
        echo 'building the app' 
      }
    }
    stage ('Test') {
      when {
        expression {
          params.executeTests
        }
      }
      steps {
        echo 'testing the app'
      }
    }
    stage ('deploy') {
      steps {
        echo 'deploying'
        echo "deploying version ${params.VERSION}"
      }
    }
  }
}
