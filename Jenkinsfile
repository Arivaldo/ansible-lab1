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
            ansiblePlaybook('./playbook_1.yml') {
                #inventoryPath('hosts.ini')
                ansibleName('ansible')
                #tags('one,two')
                #credentialsId('credsid')
                #become(true)
                #becomeUser("user")
                #extraVars {
                #    extraVar("key1", "value1", false)
                #    extraVar("key2", "value2", true)
                #}
            }
        }
      }
   }
}
