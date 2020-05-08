// Define variables
def _GATSBY_URL = "https://github.com/travers58/web"
def _DIR = "pwc-dev"
def SURGE_LOGIN = "tommassie@hotmail.com"
def SURGE_DOMAIN = "tm008558.surge.sh"

// Work
parallel repos.collectEntries {
    ["https://github.com/pwc-doit/devops", "https://github.com/travers58/web"]
   }
pipeline {
   agent any
   triggers { pollSCM('H/15 * * * *')
       }
   stages {
     stage('Checkout') {
      steps {
          sh label: '', script: """
          if [ -d "$_DIR" ]; then
            echo "Removing existing project files."
            rm -rf "$_DIR"
            echo "Re-Loading Project"
            gatsby new "$_DIR" "$_GATSBY_URL"
          else
            echo "Loading project"
            gatsby new "$_DIR" "$_GATSBY_URL"
          fi"""
         }
       }
      stage('Build') {
        steps {
          dir ("${_DIR}") {
           sh label: '', script: '''
               gatsby build'''
          }
       }
     }
     stage('Release') {
      steps {
          withCredentials([string(credentialsId: 'surge_token', variable: 'surge_t')]) {
          dir ("${env.WORKSPACE}/${_DIR}/public") {
            sh label: '', script: """
            echo 'machine surge.surge.sh
                login tommassie@hotmail.com' | tee ~/.netrc
            echo '    password' "$surge_t" | tee -a ~/.netrc
            surge --project . --domain tm008558.surge.sh
            """
            }
          }
        }
      }
    }
  }