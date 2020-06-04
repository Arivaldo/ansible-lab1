#!groovy
pipeline {
   agent any

   stages {
      stage('Verifica Ansible') {
         steps {
            echo 'Hello Ansible'
            sh 'ansible all -m ping'
         }
      }
   }
}
