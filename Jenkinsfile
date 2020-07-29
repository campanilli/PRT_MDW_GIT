pipeline {
	agent any
	stages {
	stage('Container Manager'){
		steps{
		parallel (
			"1": {
				sh ("echo test2")
			},
			"2": {
				sh ("echo test22")
			}
		)
		}
	}
	stage('Proxy'){
		steps{
		parallel (
			"1": {
				sh ("echo test2")
			},
			"2": {
				sh ("echo test22")
			}
		)
		}
	}
	stage('Database'){
		steps{
		parallel (
			"1": {
				sh ("echo test2")
			},
			"2": {
				sh ("echo test22")
			}
		)
		}
	}
	stage('Monitoring'){
		steps{
		parallel (
			"1": {
				sh ("echo test2")
			},
			"2": {
				sh ("echo test22")
			}
		)
		}
	}
	stage('Application'){
		steps{
		parallel (
			"1": {
				sh ("echo test2")
			},
			"2": {
				sh ("echo test22")
			}
		)
		}
	}
	stage('Versioning'){
		steps{
		parallel (
			"1": {
				sh ("echo test2")
			},
			"2": {
				sh ("echo test22")
			}
		)
		}
	}
	}
}
