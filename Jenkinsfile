pipeline {
    agent any
    
    stages {
    

        stage('deploy ansible coppy') {
            steps {
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
