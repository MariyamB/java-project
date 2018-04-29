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
            echo "Building application..."
            sh "cp /var/jenkins_home/workspace/java-pipeline/dist/rectangle-1.jar http://s3.amazonaws.com/mariyam-assignment9"
            }
        }
        }
        }
