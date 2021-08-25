pipeline {
    agent { label 'MAVEN'}
    triggers {
        cron('H * * * *')
        pollSCM('* * * * *')
    }
    stages {
        stage('scm') {
            steps {

                git branch: 'master', url: 'https://github.com/hemanthp03/maven-project.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
        success {
            archive '**/*.war'
            junit '**/TEST-*.xml'
        }
        
    }
}
