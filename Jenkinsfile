pipeline {
		agent{
			label{ 
				label'QA'
				customWorkspace'/mnt/assignment2/22Q3'
			}
		}
		stages{
			 stage('kill') {
				steps {
					sh "docker kill 22Q3"
					sh "docker rm 22Q3"
					sh "docker volume rm vol3-22q3"
				}
			} 
			stage('volume-3') {
				steps {
					sh "docker volume create vol3-22q3"
					sh "cd /mnt/assignment2/22Q3 && cp index.html /var/lib/docker/volumes/vol3-22q3/_data/"
				}
			}
			stage('docker-22Q3'){
				steps{
					sh "docker run --name 22Q3 -itdp 8080:80 -v vol3-22q3:/usr/local/apache2/htdocs/ httpd"
					sh "chmod -R 777 /var/lib/docker/volumes/vol3-22q3/_data/index.html"
					
				}
				
			
			}
		
		}
		
}
