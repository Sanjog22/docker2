pipeline {
		agent{
			label{ 
				label'built-in'
				customWorkspace'/mnt/assignment1/22Q1'
			}
		}
		stages{
			 stage('kill') {
				steps {
					sh "docker stop 22Q1"
					sh "docker rm 22Q1"
					sh "docker rmi httpd"
				
				}
			} 
			stage('docker-22Q1'){
				steps{
					sh "docker run --name 22Q1 -itdp 70:80 httpd"
					sh "chmod -R 777 /mnt/assignment1/22Q1/index.html"
					sh "cd /mnt/assignment1/22Q1 && docker cp index.html 22Q1:/usr/local/apache2/htdocs/"
				}
				
			
			}
		
		}
		
}
