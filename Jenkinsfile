pipeline {
	agent any
	stages{
		stage('Init'){
			steps{
				echo 'Init'
				echo "build number : ${env.BUILD_NUMBER}"
				sh "whoami"
			}
		}
		stage('Yarn Install && Build'){
			steps{
				echo 'Yarn Install && Build'
				echo '******************************'
			}
		}
		stage('Mvn Install'){
		    steps{
				echo 'Mvn Install'
				echo '******************************'
			}
		}
		stage('Mvn Test'){	
		    steps{
				echo 'Mvn Test'
				echo '******************************'
			}
		}
		stage('Docker Build'){
		    steps{
				echo 'Docker Build'
				echo '******************************'
			}
		}
		stage('Docker Push'){
		    steps{
				echo 'Docker Push'
				echo '******************************'
			}
		}
		stage('Deploy'){
			steps{
				echo 'Deploy'
				echo '******************************'
			}
		}
	}
}
