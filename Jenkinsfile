node {
 withCredentials([string(credentialsId: 'webhook-token', variable: 'webhook')]) {
 properties([
  pipelineTriggers(
   [$class: GenericTrigger(
     genericVariables: [
      [key: 'ref', value: '$.ref']
     ],

     causeString: 'Triggered on $ref',

     token: 'webhook',

     printContributedVariables: true,
     printPostContent: true,

     silentResponse: false,

     regexpFilterText: '',
     regexpFilterExpression: ''
   )
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