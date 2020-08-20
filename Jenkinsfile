pipeline {
  agent any
  tools {
        maven 'Maven 3.6.3'
        jdk 'jdk8'
  }
  
  options {
        timestamps()
        timeout(time: 5, unit: 'MINUTES')
  }
  
   stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
            }
        }
    }
}
