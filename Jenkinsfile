pipeline {
   agent any
   // triggers { pollSCM('H/15 * * * *')
   //     }

   // properties([pipelineTriggers([githubPush()])])


   options([pipelineTriggers([githubPush()])])


   // Work
   stages {
     stage('Checkout') {
      steps {
          build(job: "gatsby/master", 
          propagate: false, 
          wait: false,
           )
       }
     }
   }
 }