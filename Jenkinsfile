node {
withCredentials([string(credentialsId: 'webhook-token', variable: 'webhook')]) {
 properties([
  pipelineTriggers([
   [$class: 'GenericTrigger',
    token: webhook,
   ]
  ])
 ])
}
}

pipeline {
  agent any
    stages {
     stage('Checkout') {
      steps {
          build(job: "gatsby-build/smoke", 
          propagate: false, 
          wait: false,
           )
       }
     } 
   }
}