pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Ansible Deploy') {
      steps {
        sh '''
          ansible --version
          ansible-playbook ansible/deploy.yml
        '''
      }
    }
  }
}
