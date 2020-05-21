node {
withCredentials([string(credentialsId: 'webhook-token', variable: 'webhook')]) {
 properties([
  pipelineTriggers([
   [$class: 'GenericTrigger',

    causeString: 'Triggered on $ref',

    genericVariables: [
      [key: 'ref', value: '$.ref']
     ],

    [
      key: 'before',
      value: '$.before',
      expressionType: 'JSONPath', //Optional, defaults to JSONPath
      regexpFilter: '', //Optional, defaults to empty string
      defaultValue: '' //Optional, defaults to empty string
     ]
    ],
    genericRequestVariables: [
     [key: 'requestWithNumber', regexpFilter: '[^0-9]'],
     [key: 'requestWithString', regexpFilter: '']
    ],
    genericHeaderVariables: [
     [key: 'headerWithNumber', regexpFilter: '[^0-9]'],
     [key: 'headerWithString', regexpFilter: '']
    ], 

    token: webhook,
   ]
  ])
 ])
}
}

pipeline {
  agent any
    stages {
     stage('Checkout') {
      steps {
          build(job: "gatsby-build/smoke", 
          propagate: false, 
          wait: false,
           )
       }
     } 
   }
}