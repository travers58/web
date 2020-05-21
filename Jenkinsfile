pipeline {
  agent any
  parameters {
  withCredentials([string(credentialsId: 'webhook-token', variable: 'webhook')]) {
  }  
  triggers {
    GenericTrigger(
     genericVariables: [
      [key: 'ref', value: '$.ref']
     ],

     causeString: 'Triggered on $ref',

     token: webhook,

     printContributedVariables: true,
     printPostContent: true,

     silentResponse: false,

     regexpFilterText: '',
     regexpFilterExpression: ''
    )
    }
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