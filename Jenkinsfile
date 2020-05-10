pipeline {
   agent any

   triggers {
        githubPush()
    }

   // Work
   stages {
     stage('Checkout') {
      steps {
          build(job: "build/smoke", 
          propagate: false, 
          wait: false,
           )
       }
     }
   }
 }