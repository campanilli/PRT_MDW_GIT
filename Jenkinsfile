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
	parallel (
	"1": {
		sh ("echo test2")
	},
	"2": {
		sh ("echo test22")
	}
	)
	}
	stage('Database'){
	steps{
		echo 'test3'
	}
	}
	stage('Monitoring'){
	steps{
		echo 'test4'
	}
	}
	stage('Application'){
	steps{
		echo 'test5'	
	}
	}
	stage('Versioning'){
	steps{
		echo 'test6'
	}
	}
}
}
