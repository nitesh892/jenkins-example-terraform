pipeline {
    agent any
  stages{
    stage('clean workspace') {
      steps {
        cleanWs()
      }
    }
    stage('checkout') {
      steps {
        checkout scm
      }
    }
    stage('terraform') {
      steps {
        sh './terraformw apply -auto-approve -no-color'
      }
    }
  post {
    always {
      cleanWs()
    }
  }
    stage('Plan') {
            steps {
                script {
                    currentBuild.displayName = params.version
                }
                sh 'terraform init '
            }
        }
  }
  }
