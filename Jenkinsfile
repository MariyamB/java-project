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
       sh "rectangle-71.jar s3://mariyam-assignment9/ --recursive"
      }
   }
  }
