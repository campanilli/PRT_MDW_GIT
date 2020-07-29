pipeline {
	agent any
	stages {
	stage('Container Manager'){
		steps{
		parallel (
			"PORTAINER": {
				sh "echo PORTAINER"
			}
		)
		}
	}
	stage('Proxy'){
		steps{
		parallel (
			"APACHE2": {
				sh ("echo APACHE2")
			},
			"HAPROXY": {
				sh ("export version='0'; export image1='hypriot/rpi-haproxy'; export name='haproxy'; export init='202006191713'; export port1='8089'; export port2='80'; cd /home/pi/CAMPANILLI/scripts; ./PRT_MDW_DOCKER_APP_0.0.1.sh")
			},
			"NGINX": {
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
