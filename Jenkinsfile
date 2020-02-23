pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        stage('Test'){
            steps {
                sh 'mvn test'    
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'    
                }
            }
        }
<<<<<<< HEAD
        stage('Delivery'){
=======
        state('Delivery'){
>>>>>>> 68c27d8336be80c5263b7241f78903e902d7e2d3
            steps {
                sh './jenkins/scripts/deliver.sh'    
            }    
        }
    }
}
