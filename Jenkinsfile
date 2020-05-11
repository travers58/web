pipeline {
   agent any

   triggers {
        githubPush()
    }

   // Work
   stages {
     stage('Checkout') {
      steps {
          build(job: "dev-test/smoke", 
          propagate: false, 
          wait: false,
           )
       }
     }
   }
 }