pipeline {
	agent any 

stages {
	
  stage('Git pull'){
	  steps{
  		git branch: 'master', 
  		credentialsId: 'gitID', 
  		url: 'https://github.com/KhaleelMak/Jenkinsfile_porj.git'
		}
	}
	stage('Validate'){
		steps {
		echo 'Validating the source code..'
		sh 'mvn validate'
		}
	}

	stage('Test'){
	steps{
	echo 'Testing the code..'
	sh 'mvn test'
		}
	}
	stage('Compile'){
	steps{
	echo 'Compile..'
	sh 'mvn compile'
	}
	}

	stage('Package'){
	steps{
	echo 'Creating .war file'
	sh 'mvn package'
	}
	}
	
	stage('Deploy to Nexus'){
	    steps{
	        echo 'Deploying to nexus'
	        sh 'mvn deploy'
	        
	    }
	}
}
}

