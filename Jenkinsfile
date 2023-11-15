pipeline{
    
    agent any
        
        stage("build") {
            steps {
                sh "./mvnw package"
            }
        }
        
        stage("capture") {
            steps {
                archiveArtifacts '**/target/*.jar'
                jacoco()
                junit 'target/surefire-reports/TEST*.xml'
            }
        }
    
    }
}