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
        dir("${env.WORKSPACE}/ansible") { 
          sh '''
            # 使用 ansible.cfg
            ansible-playbook -i inventory.ini deploy.yml \
              -e "ansible_ssh_common_args='-o ControlMaster=no -o ControlPersist=no'"
          '''
        }
      }
    }
  }
}
