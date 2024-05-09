def code
pipeline {
	agent any
	environment {
		GITHUB_TOKEN = credentials('github')
	}
	stages {
		stage('stage 1') {
			steps {
				sh 'echo "stage 1"'
				script {
					code = load 'scripts/hello.groovy'
					code.example1()
				}
			}
		}
		stage('stage 2') {
			steps {
				sh 'echo "stage 2"'
				script {
					code.example2()
				}
                                sh('git clone https://github.com/Redd-devel/dbox_sync.git')
				sh 'cd dbox_sync; chmod +x main.py; ls -l'
			}
		}
	}
}
