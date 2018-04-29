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
            sh "ant -f build.xml -v"
            }
        }
        }
        }
