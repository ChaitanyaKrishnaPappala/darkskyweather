pipeline {
	agent any
	stages {
		stage('Clone Git Repo'){
				steps{
					git branch: 'pipeline',
					    url:'https://github.com/IftikharZulfiqar/darkskyweather.git'
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
					sh 'yarn start &'	
				}
		}
		stage('Run Tests'){
				steps{
					sh 'yarn cypress run -b chrome -c cypress/integration/*.js'
				}
		}	
        
		stage('deploy'){
				steps{
					echo "Deployment"					
					sh 'tar cvxf cypressPipeline2-$BUILD_NUMBER.tar.gz'
				}
		}	
	}
}
