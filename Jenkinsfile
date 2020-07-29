pipeline {
    agent any
    stages {

        stage('Container Manager'){
          steps{
		    echo 'test1'
                sh 'mkdir from-jenkins'
                sh 'touch from-jenkins/test.txt'
                }
        }
	stage('Proxy'){
		echo 'test2'
	}
	stage('Database'){
		echo 'test3'
	}
	stage('Monitoring'){
		echo 'test4'
	}
	stage('Application'){
		echo 'test5'	
	}
	stage('Versioning'){
		echo 'test6'
	}
}
}
