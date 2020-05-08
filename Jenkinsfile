pipeline {
   agent any
   triggers { pollSCM('H/15 * * * *')
       }
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