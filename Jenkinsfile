#!groovy
pipeline {
   agent any

   stages {
      stage('Ckeckout do Playbook') {
         steps {
            echo 'Checking out playbook'
            git url: 'git@github.com:Arivaldo/ansible-lab1.git', branch: 'master', credentialsId: 'GitHubArivaldo' 
            sh 'ls'
         }
      }
      stage('Play') {
        steps {
            ansiblePlaybook(playbook: './playbook_1.yml') {
                
            }
        }
      }
   }
}
