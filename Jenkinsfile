pipeline {
    agent {
        docker { image 'liquibase/liquibase:4.9.1' }
    }
    
    environment {
        PostgresDB_Creds=credentials('PGdb_credentials')
    }
    
    stages{
        stage('Status') {
            steps {
                sh 'liquibase status --url = "jdbc:mysql://localhost:3306/liquibase" --changeLogFile=src/main/script/changelog-master.xml --liquibasePropertiesPath=src/main/resources/liquibase.properties'
            }
        }
        stage('Update') {
            steps {
                sh 'liquibase update --url = "jdbc:mysql://localhost:3306/liquibase" --changeLogFile=src/main/script/changelog-master.xml --liquibasePropertiesPath=src/main/resources/liquibase.properties'
            }
        }
        
    }
    post {
        always {
            cleanWs()
        }
    }
}
