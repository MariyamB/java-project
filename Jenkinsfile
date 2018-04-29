pipeline {
 agent {
  label 'linux'
 }
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
node('linux') {
 withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'faef8bbd-5e46-476c-b068-792910928c13', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])
  {
  stage("Deploy") {
   sh "aws s3 cp /workspace/java-pipeline/dist/ s3://mariyam-assignment10/ --recursive"
  }
  stage("Report") {
   sh "aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins"
  }
 }
}
