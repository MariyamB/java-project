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
    node('linux')
{
 stage("Deploy") {
    withCredentials([
     [$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '5eb9f71b-ee0c-4225-9e96-0cbde8f8daaa', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']
    ]) {
       sh 'aws s3 cp ./var/jenkins_home/workspace/java-pipeline/dist/rectangle-46.jar s3://mariyam-assignment9/ --recursive us-east-1'
    }
 }
}
}


def deploy_prod() {
    sh 'aws s3 cp ./var/jenkins_home/workspace/java-pipeline/dist/rectangle-46.jar s3://mariyam-assignment9/ --recursive'
}
