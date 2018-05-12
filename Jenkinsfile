properties([pipelineTriggers([githubPush()])])
node('linux') {
        stage('TestNew') {
                git credentialsId: 'e5ee4c3e-22c3-4360-aa88-2fa80dda1cce', url: 'https://github.com/MariyamB/java-project.git'
                sh 'ant -buildfile test.xml'
        }
        stage('Build') {
                sh 'ant'
        }
        stage('Results') {
                junit 'reports/*.xml'
        }
