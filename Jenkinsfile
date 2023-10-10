pipeline {
    agent any
    
    environment {
        PATH = "/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin" // Thiết lập biến môi trường PATH cho Jenkins
    }
    
    stages {
        stage('Deploy Spring Boot to DEV') {
            steps {
                script {
                    sh 'apt install -y software-properties-common' // -y để tránh xác nhận yêu cầu
                    sh 'apt-add-repository --yes --update ppa:ansible/ansible'
                    sh 'apt install -y ansible'
                    sh 'ansible-playbook -i hosts playbook.yml'
                }
            }
        }
    }
    
    post {
        always {
            cleanWs()
        }
    }
}
