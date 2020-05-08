pipeline {

 agent any
 tools {
        gradle "gradle-5.2.1"
    }
 
  options {
     skipDefaultCheckout()
  }
	
  stages {
  
	stage('Checkout from GIT') {
        steps {
           	script {
					git branch: "${BRANCH}", credentialsId: '	7f4298e8-bbd6-4280-b629-4c1206ce3147', url: 'https://github.com/Gayathri-MG/Gradle-build.git'
				    gitInfo = checkout scm
                    echo "Current Branch : $gitInfo.GIT_COMMIT"
					println gitInfo
            }
        }
    }
	  stage('Build') {
		steps {
			script {
				sh '''
				
				cd ${WORKSPACE}
				gradlew build
				'''
			}
		}
	}
	 
  }
}
