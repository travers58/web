pipeline {
   agent any
   // triggers { pollSCM('H/15 * * * *')
   //     }
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