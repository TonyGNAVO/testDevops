node{


	stage('SCM'){
	git 'https://github.com/at0myst1c/testDevops'
	}


	stage('Compile'){
	def mvnHome= tool name : 'maven-3', type :'maven'
	sh "${mvnHome}/bin/mvn package -Dmaven.test.skip=true"
	}

	stage('SonarQube'){
	def mvnHome = tool name:'maven-3', type:'maven'
	sh "${mvnHome}/bin/mvn sonar:sonar -Dsonar.host.url = http://172.17.192.193:9000"
	}



}
