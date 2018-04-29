pipeline {
agent {label 'linux'}
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
  }
  }
  node('linux')
  {
   stage("Deploy") {
      withCredentials([
       [$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '5eb9f71b-ee0c-4225-9e96-0cbde8f8daaa', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']
      ]) {
       sh "aws s3 cp /workspace/java-pipeline/dist/ s3://mariyam-assignment9/ --recursive"
      }
   }
   stage("Report")
   {
   sh "aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins-stack"

   }
  }
