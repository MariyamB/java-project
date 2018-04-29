#!groovy
node {
    stage('check environment') {
    if (env.BRANCH_NAME=="master") {
            env.DEV_ENV = "production"
        }
        env.NODE_ENV = "${env.DEV_ENV}"
    }

    stage('checkout') {
        checkout scm
    }

    stage('clean') {
    echo "Testing application..."
    sh "ant -f test.xml -v"
    }

    stage('build') {
    echo "Testing application..."
    sh "ant -f build.xml -v"
    }

    stage('deploy') {
    echo 'deploy the application'
            deploy_prod()
    }
}


def deploy_prod() {
    sh 'aws s3 cp ./var/jenkins_home/workspace/java-pipeline/dist/rectangle-46.jar s3://mariyam-assignment9/ --recursive us-east-1'
}
