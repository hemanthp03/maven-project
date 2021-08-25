pipeline {
	agent {label 'MAVEN'}
	stages {
		stage('scm') {
			steps {
			
				git branch: 'master', url: 'https://github.com/hemanthp03/maven-project.git'
			}
		}
		stage('build') {
			steps {
				sh 'mvn clean install'	
			}
		}
	}
	post {
		sucess {
			artifacts '**/*.war'
			junit '**/TEST-*.xml'
		}
	}
}
