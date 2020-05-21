pipeline {
  agent any
  triggers {
    GenericTrigger(
     genericVariables: [
      [key: 'ref', value: '$.ref']
     ],

     causeString: 'Triggered on $ref',

     token: 'abc123',

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