pipeline {
   agent any

   triggers {
        githubPush()
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