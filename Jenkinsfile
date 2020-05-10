pipeline {
   agent any
   // triggers { pollSCM('H/15 * * * *')
   //     }

   triggers {
        githubPush()
    }

   // Work
   stages {
     stage('Checkout') {
      steps {
          build(job: "gatsby/smoke", 
          propagate: false, 
          wait: false,
           )
       }
     }
   }
 }