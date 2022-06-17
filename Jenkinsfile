pipeline {
    agent any 
    stages {
        stage('Stage 1') {
            steps {
                echo 'clone the repo'
                sh 'rm -fr html'
                sh 'git clone https://github.com/jaingaurav126/html.git'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'connect to remote host and pull down the latest version'
                sh 'ssh -i ~/working.pem ec2-user@3.8.78.82 sudo git -C /var/www/html pull'
            }
        }
        stage('Stage 3') {
            steps {
                echo 'Check website is up'
                sh 'curl -Is 3.8.78.82 | head -n 1'
            }
        }
    }
}
