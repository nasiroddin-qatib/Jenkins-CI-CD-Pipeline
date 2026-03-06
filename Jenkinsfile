pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/nasiroddin-qatib/ci-nexus'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }


	stage('Sonarqube') {
	    steps { 
	      withSonarQubeEnv('sonarqube') {
		sh 'mvn sonar:sonar'
	    }
	} 
}

	stage('Quality Gate') {
	    steps {
		waitForQualityGate abortPipeline: true
	    }
	}

        stage('Package') {
            steps {
                sh 'mvn clean package'
            }

        }


	stage('deploy') {
	    steps {
		sh 'mvn deploy'

		}
	}


	stage('deploy to tomcat') {
	    steps {
		deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat', path: '', url: 'http://13.127.127.130:8080/')], contextPath: 'myapp', onFailure: false, war: '**/*.war'



	}
}

    }
}

