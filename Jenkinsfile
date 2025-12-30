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
        dir("${env.WORKSPACE}") { // 切换到工作目录
          sh '''
            # 使用工作目录下的 ansible.cfg
            export ANSIBLE_CONFIG=${WORKSPACE}/ansible.cfg
            
            # 查看 ansible 配置是否生效
            ansible --version
            
            # 执行 playbook
            ansible-playbook -i inventory.ini playbook.yml
          '''
        }
      }
    }
  }
}
