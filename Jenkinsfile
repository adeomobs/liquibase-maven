pipeline {
    agent {
        docker { image 'liquibase/liquibase:4.4.2' }
    }
    
    environment {
        DB_Creds=credentials('db_credentials')
    }
    stages{
        stage('Status') {
            steps {
                sh 'liquibase status --url = "jdbc:mysql://localhost:3306/liquibase"'
            }
        }
        stage('Update') {
            steps {
                sh 'liquibase update --url = "jdbc:mysql://localhost:3306/liquibase"'
            }
        }
        
    }
    post {
        always {
            cleanWs()
        }
    }
}
