pipeline{
		agent{
			label{ 
				label 'built-in'
				customWorkspace '/mnt/project/assignment1/22Q1'
			}
		}
		Stages{
			/* stage('kill') {
				steps {
					sh "docker kill 22Q1"
					sh "docker rm 22Q1"
					sh "docker rmi httpd"
				}
			} */
			Stage('docker-22Q1') {
				Steps {
					sh "docker run --name 22Q1 -itdp 70:80 httpd"
					sh "chmod -R 777 /mnt/project/assignment1/22Q1/index.html"
					sh "cd /mnt/project/assignment1/22Q1 && docker cp index.html 22Q1:/usr/local/apache2/htdocs/"
				}
				
			
			}
		
		}
		
}
