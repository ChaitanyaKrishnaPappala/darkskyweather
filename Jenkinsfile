pipeline {
	agent any
	stages {
		stage('Clone Git Repo'){
				steps{
					git 'https://github.com/IftikharZulfiqar/darkskyweather.git'
		    }
		}
		stage('Install Dependencies'){
				steps{
					
					sh 'npm install'
					sh 'npm install --global yarn'
				}
		}
		stage('build project') {
				steps {
					sh 'yarn install'
									
				}
        }
		stage('StartApp') {
				steps {
					
					sh 'yarn start & echo $! > $WORKSPACE/StartApp.pid; wait -n $(cat $WORKSPACE/StartApp.pid) || true'
					echo $WORKSPACE/StartApp.pid
									
				}
		stage('Run Tests'){
				steps{
					sh 'yarn cypress'
				}
		}		
	}
}
