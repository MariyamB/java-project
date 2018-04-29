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
            sh "pip install admin awscli"
            sh "export AWS_ACCESS_KEY_ID=AKIAITPOT665WE22XUZQ"
            sh "export AWS_SECRET_ACCESS_KEY=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"
            sh "aws s3 cp /var/jenkins_home/workspace/java-pipeline/dist/rectangle-1.jar http://s3.amazonaws.com/mariyam-assignment9"
            }
        }
        }
        }
