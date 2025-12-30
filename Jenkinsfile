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
          # 指定 ansible.cfg 文件
          export ANSIBLE_CONFIG=/var/jenkins_home/ansible.cfg
          
          # 查看 ansible 配置是否生效
          ansible --version
          
          # 执行 playbook
          ansible-playbook -i inventory.ini playbook.yml
        '''
      }
    }
  }
}
