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
					
					echo "Installion"
				}
		}
		stage('build project') {
				steps {
					echo " Build"
									
				}
        }
		stage('StartApp') {
				steps {
					
					sh 'yarn start &'
					
									
				}
		}
		stage('Run Tests'){
				steps{
					sh 'yarn cypress'
				}
		}		
	}
}
