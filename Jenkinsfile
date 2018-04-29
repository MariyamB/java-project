
            node('linux') {
            stage ("Test"){
            steps {
            withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '5eb9f71b-ee0c-4225-9e96-0cbde8f8daaa', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
        sh 'aws cloudformation describe-stack-resources --stack-name jenkins-stack --region us-east-1'
    }

        }
        }
        }
