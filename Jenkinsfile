pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/SmokyNight/AnsibleLabs.git']]])
            }
        }
        stage('Build') {
            steps {
                sh 'sudo ansible-playbook AnsibleLab2_6.yaml --extra-vars "hosts='${hostsToDeploy}'" --user ec2-user --key-file /home/ec2-user/.ssh/id_rsa'
            }
        }
        
    }
}
