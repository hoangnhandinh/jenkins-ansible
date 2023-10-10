pipeline {
    agent any
    
    stages {
    

        stage('deploy ansible coppy') {
            steps {
                    sh 'sudo apt install software-properties-common'
                    sh 'sudo apt-add-repository --yes --update ppa:ansible/ansible'
                    sh 'sudo apt install ansible'
                    sh 'ansible-playbook -i hosts --private-key ansible_key playbook.yml'
            }
        }
        
    }
    post {
        // Clean after build
        always {
            cleanWs()
        }
    }
}
