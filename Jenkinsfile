pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Git') {
            steps{
                git branch: 'main', credentialsId: 'd961d514-ae80-4f6c-a625-ee62bb36ce66', url: 'https://github.com/Mrachneyshiy/dev-17_ansible-04-role-mrachneyshiy.git'
            }
        }
        stage('Molecule install') {
            steps{
                sh 'pip3 install molecule==3.4.0'
                sh 'pip3 install ansible-lint==5.1.3'
                sh 'pip3 install molecule_docker'
            }
        }
        stage('Molecule test'){
            steps{
                dir('roles/vector-role/') {
                    sh 'ls -l'
                    sh 'molecule test'
                    cleanWs()
                }
            }
        }
    }
}
