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
            stage("Deploy")
            {
              steps {
            withAwsCli(
         AWS_ACCESS_KEY_ID=AKIAITPOT665WE22XUZQ,
         AWS_SECRET_ACCESS_KEY=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,
         defaultRegion: 'us-east-1'])
         {

        sh "
           aws s3 cp /var/jenkins_home/workspace/java-pipeline/dist/rectangle-1.jar http://s3.amazonaws.com/mariyam-assignment9/"
        }
        }
        }
        }
