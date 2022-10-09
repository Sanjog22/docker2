pipeline {
		agent{
			label{ 
				label'built-in'
				customWorkspace'/mnt/assignment2/22Q2'
			}
		}
		stages{
			 stage('kill') {
				steps {
					sh "docker kill 22Q2"
					sh "docker rm 22Q2"
					
				}
			} 
			stage('volume-2') {
				steps {
					sh "docker volume create vol2-22q2"
					sh "cd /mnt/assignment2/22Q2 && cp index.html /var/lib/docker/volumes/vol2-22q2/_data/"
				}
			}
			stage('docker-22Q2'){
				steps{
					sh "docker run --name 22Q2 -itdp 80:80 -v vol2-22q2:/usr/local/apache2/htdocs/ httpd"
					sh "chmod -R 777 /var/lib/docker/volumes/vol2-22q2/_data/index.html"
					
				}
				
			
			}
		
		}
		
}
