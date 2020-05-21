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

     regexpFilterText: '$ref',
     regexpFilterExpression: 'refs/heads/' + BRANCH_NAME
    )
    }
    stages {
     stage('Checkout') {
      steps {
          build(job: "gatsby-build/master", 
          propagate: false, 
          wait: false,
           )
       }
     } 
   }
}