pipeline{

agent any

tools{
maven 'maven-3.8.4'

}

triggers{
pollSCM('* * * * *')
}

options{
timestamps()
buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5'))
}

stages{

  stage('CheckOutCode'){
    steps{
	git branch: 'main', url: 'https://github.com/DevopsTraining-Harish/flip-web-app.git'
	}
  }
stage('compile'){
  steps{
  sh  "mvn clean package"
  }
  }

stage('clenaup workspace'){
	steps{
		cleanWs()
	}
}
	
}  
}//Pipeline closing
