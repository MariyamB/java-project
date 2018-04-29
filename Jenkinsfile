pipeline {
    agent any
    stages {
    stage("Unit Test") {
    steps {
    echo "Testing application..."
    sh "ant -f test.xml -v"
          }
          }
          stage("Build") {
          steps {
          echo "Testing application..."
          sh "ant -f build.xml -v"
            }
            }
            stage ('Test'){
            steps {
            withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AKIAJW3ALQSE4WWHK4MA', credentialsId: '14dd1bff-3295-4649-a919-3fc6ad57f627', secretKeyVariable: '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']])
		sh 'aws cloudformation describe-stack-resources --stack-name jenkins-stack --region us-east-1'

        }
        }
        }
        }
