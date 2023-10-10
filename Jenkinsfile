pipeline {
    agent any
    
    stages {
        stage('Deploy Spring Boot to DEV') {
            steps {
                sh 'sudo apt install software-properties-common'
                sh 'sudo apt-add-repository --yes --update ppa:ansible/ansible '
                sh 'sudo apt install ansible'
                sh 'ansible-playbook -i hosts playbook.yml'
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
