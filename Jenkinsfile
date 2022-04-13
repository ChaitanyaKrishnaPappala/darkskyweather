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
					
					sh 'yarn start & | awk {print $1}'
					
									
				}
		}
		stage('Run Tests'){
				steps{
					sh 'yarn cypress'
				}
		}		
	}
}
