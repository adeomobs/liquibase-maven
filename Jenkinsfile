pipeline {
    agent {
        docker { image 'liquibase/liquibase:4.4.2' }
    }
    stages{
            stage('test') {
                steps {
                    sh 'liquibase --version'
                }
            }
     }
}
