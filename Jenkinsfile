pipeline {
    agent any
    tools {
        nodejs 'Node 6.x'
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
		    }
	    }
     }
}
