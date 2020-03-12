pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat './mvnw clean'
      }
    }

    stage('Test') {
      steps {
        bat './mvnw test'
      }
    }

    stage('Package') {
      steps {
        bat './mvnw package'
      }
    }

    stage('Deploy') {
          when {
    expression {
        return env.BRANCH_NAME != 'master';
        }
    }      
      steps {
        bat './mvnw deploy'
      }
    }

  }
}