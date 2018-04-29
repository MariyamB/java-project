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
		sh 'aws cloudformation describe-stack-resources --stack-name jenkins --region us-east-1'

        }
        }
        }
