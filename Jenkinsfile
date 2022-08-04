pipeline{
	agent{
		label'built-in'
		customWorkspace '/mnt/dir1'
		}
		stages {
		stage('master'){
		steps {
			sh 'git clone https://github.com/dev-tecki/new1.git -b master'
			sh 'chmod 777 -R /mnt/dir1/index.html'
			sh 'docker run -itdv /mnt/dir1:/usr/local/htdocs/ -p 81:80 httpd'
		}
		}
		stage('DEV'){
		steps {
		dir ('/mnt/dev'){
			sh 'git clone https://github.com/dev-tecki/new1.git -b DEV'
			sh 'chmod 777 -R /mnt/dev/index.html'
			sh 'docker run -itdv /mnt/dev:/usr/local/htdocs/ -p 82:80 httpd'
			}
		}
		steps {
		dir ('/mnt/qa'){
			sh 'git clone https://github.com/dev-tecki/new1.git -b QA'
			sh 'chmod 777 -R /mnt/qa/index.html'
			sh 'docker run -itdv /mnt/qa:/usr/local/htdocs/ -p 80:80 httpd'
			}
		}
}
}
}
