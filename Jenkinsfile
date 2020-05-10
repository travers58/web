pipeline {
   agent any

   triggers {
        githubPush()
    }

   // Work
   stages {
     stage('Checkout') {
      steps {
          build(job: "build/master", 
          propagate: false, 
          wait: false,
           )
       }
     }
   }
 }