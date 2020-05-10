pipeline {
   agent any

   triggers {
        githubPush()
    }

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