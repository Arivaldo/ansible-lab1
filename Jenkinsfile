#!groovy
pipeline {
   agent any

   stages {
      stage('Ckeckout do IaC') {
         steps {
            echo 'Checking out playbook'
            git url: 'git@github.com:Arivaldo/ansible-lab1.git', branch: 'master', credentialsId: 'GitHubArivaldo' 
            sh 'ls'
         }
      }
      stage('Verificando Instâncias e Imagens') {
        steps {
            ansiblePlaybook playbook: './playbook_1.yml', installation: 'ansible',  colorized: true
        }
      }
      stage('Inicializando Whoami') {
        steps {
            ansiblePlaybook playbook: './playbook_2.yml', installation: 'ansible',  colorized: true
        }
      }
      stage('Testando Whoami') {
        agent {
           docker {
              image 'httpd:alpine'
           } 
        }   
        steps {
          sh "ab -n 1000 -c 500 https://tecvaldo-pro.matrix.net/whoami"
        }
      }
      
   }
}
