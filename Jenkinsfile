pipeline {
    agent any
    stages {
        stage("SCM clone"){
            steps {
                git branch: 'feature', credentialsId: 'git-login', url: 'https://github.com/hiyu12/ansible.git'
            }
        }
        stage("Ansible"){
            steps {
                ansiblePlaybook credentialsId: 'private-key', disableHostKeyChecking: true, installation: 'ansible-ak', inventory: 'inven', playbook: 'apache.yaml'
            }
        }
    }
}
