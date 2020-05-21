pipeline {
   agent any

   // triggers {
   //      githubPush()
   //  }

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

      regexpFilterText: '', 
      regexpFilterExpression: ''
    )
  }   

   // Work
   stages {
     stage('Checkout') {
      steps {
          build(job: "dev-test/master", 
          propagate: false, 
          wait: false,
           )
       }
     }
   }
 }