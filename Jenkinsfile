pipeline {
    agent
    stages {
        stage ('Checkout') {
          steps {
            git 'https://github.com/Ashish-Dalvi/spring-petclinic.git'
          }
        }
        stage('Build') {
            agent { docker 'maven:3.5-alpine' }
            steps {
                sh 'mvn clean package'
                junit '**/target/surefire-reports/TEST-*.xml'
		}
	}
   }
}
