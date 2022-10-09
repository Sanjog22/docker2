pipeline {
		agent{
			label{ 
				label'built-in'
				customWorkspace'/mnt/assignment2/22Q1'
			}
		}
		stages{
			 stage('kill') {
				steps {
					sh "docker kill 22Q1"
					sh "docker rm 22Q1"
					
				}
			} 
			stage('volume-1') {
				steps {
					sh "docker volume create vol1-22q1"
					sh "cd /mnt/assignment2/22Q1 && cp index.html /var/lib/docker/volumes/vol1-22q1/_data/"
				}
			}
			stage('docker-22Q1'){
				steps{
					sh "docker run --name 22Q1 -itdp 70:80 -v vol1-22q1:/usr/local/apache2/htdocs/ httpd"
					sh "chmod -R 777 /var/lib/docker/volumes/vol1-22q1/_data/index.html"
					
				}
				
			
			}
		
		}
		
}
