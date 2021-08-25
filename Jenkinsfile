pipeline {
	agent {label 'MAVEN'}
	triggers {
		cron('H * * * *')
		pollscm('* * * * *')
	}
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
	    success {
			artifacts '**/*.war'
			junit '**/TEST-*.xml'
		}
	}
}
