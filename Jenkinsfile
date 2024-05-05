def code
pipeline {
	agent any
	environment {
		GITHUB_TOKEN = credentials('github-token')
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
				git credentialsId: env.GITHUB_TOKEN, url: 'https://github.com/Redd-devel/dbox_sync.git'
				sh 'ls -l dbox_sync'
			}
		}
	}
}
