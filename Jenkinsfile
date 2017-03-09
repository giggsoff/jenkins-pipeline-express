pipeline {
    agent any
    tools {
        nodejs 'node'
    }
    stages{
	    stage('Initialize') {
		    steps{
			echo 'Initializing...'
		    }
	    }

	    stage('Checkout') {
		    steps{
			echo 'Getting source code...'
			checkout scm
		    }
	    }

	    stage('Build') {
		    steps{
			echo 'Building dependencies...'
			sh 'npm i'
		    }
	    }

	    stage('Test') {
		    steps{
			echo 'Testing...'
			sh 'npm test'
		    }
	    }

	    stage('Publish') {
		    steps{
			echo 'Publishing Test Coverage...'
			publishHTML (target: [
				allowMissing: false,
				alwaysLinkToLastBuild: false,
				keepAll: true,
				reportDir: 'coverage/lcov-report',
				reportFiles: 'index.html',
				reportName: "Application Test Coverage"
			])
		    }
	    }
     }
}
