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
				sh ("export version='0'; export image1='hypriot/rpi-haproxy'; export name='haproxy'; export init='202006191713'; export port1='8089'; export port2='80'; cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; ./PRT_MDW_DOCKER_APP_0.0.1.sh")
			},
			"NGINX": {
				sh ("export version='0'; export image1='nginx'; export name='nginx'; export init='202006191452'; export port1='7001'; export port2='80'; cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; ./PRT_MDW_DOCKER_APP_0.0.1.sh")
			}
		)
		}
	}
	stage('Database'){
		steps{
		parallel (
			"INFLUXDB": {
				sh ("export version='0'; export image1='influxdb'; export name='influxdb'; export init='latest'; export port1='8086'; export port2='8086'; export net=influxdb; cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; ./PRT_MDW_DOCKER_APP_0.0.2.sh")
			},
			"MYSQL": {
				sh ("export version='0'; export image1='hypriot/rpi-mysql'; export name='mysql-wordpress'; export init='latest'; export passwd=Aa.12345678; cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; ./PRT_MDW_DOCKER_APP_0.0.6.sh")
			}
		)
		}
	}
	stage('Monitoring'){
		steps{
		parallel (
			"CHRONOGRAF": {
				sh ("export version='0'; export image1='chronograf'; export name='chronograf'; export init='latest'; export port1='8888'; export port2='8888'; export net=influxdb; export url=influxdb; cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; ./PRT_MDW_DOCKER_APP_0.0.3.sh")
			},
			"GRAFANA": {
				sh ("export version='0'; export image1='fg2it/grafana-armhf'; export name='grafana'; export init='202006191826'; export port1='3001'; export port2='3000'; cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; ./PRT_MDW_DOCKER_APP_0.0.1.sh")
			},
			"JENKINS": {
				sh ("export version='0'; export image1='kosmoflyko/rpi-jenkins'; export name='jenkins'; export init='202003302132'; export port1='8084'; export port2='8080'; export port3='50000'; export port4='50000'; cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; ./PRT_MDW_DOCKER_APP_0.0.4.sh")
			},
			"MONITORIX": {
				sh ("export version='0'; export image1='jpdus/rpi-monitorix'; export name='monitorix'; export init='202006191529'; export port1='6002'; export port2='8080'; cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; ./PRT_MDW_DOCKER_APP_0.0.1.sh")
			},
			"ZABBIX": {
				sh ("export version=0; export image1=zmartell/rpi-zabbix; export name=zabbix; export init=latest; export port1=2812; export port2=2812; export port3=10051; export port4=10051; export port5=10052; export port6=10052; export port7=80; export port8=80; cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; ./PRT_MDW_DOCKER_APP_0.0.7.sh")
			}
		)
		}
	}
	stage('Application'){
		steps{
		parallel (
			"WORDPRESS": {
				sh ("export version='0'; export image1='wordpress'; export name='wordpress'; export init='202006292050'; export port1='8001'; export port2='80'; cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; ./PRT_MDW_DOCKER_APP_0.0.1.sh")
			}
		)
		}
	}
	stage('Versioning'){
		steps{
		parallel (
			"GITHUB": {
				sh ("cd /var/lib/jenkins/workspace/PRT_MDW_GIT/PRT_MDW_GIT_0.0.1; git config --global user.email 'thiago.campanilli@gmail.com'; bash PRT_MDW_GIT_0.0.1.sh")
			}
		)
		}
	}
	}
}
