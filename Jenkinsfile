properties([pipelineTriggers([githubPush()])])

node('linux') {   
	stage('TestNew') {    
		git 'https://github.com/MariyamB/java-project.git'
		sh 'ant -buildfile test.xml'   
	}   
	stage('Build') {    
		sh 'ant'   
	}   
	stage('Results') {    
		junit 'reports/*.xml'   
	}
}

