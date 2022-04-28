pipeline {
    agent { 
        node {
             label 'master' 
        }
    }
    stages{
            stage('Checkout') {
                git url: 'https://github.com/adeomobs/liquibase-maven.git', credentialsId: 'adeomobs', branch: 'master'
            }
            stage('Update') {
                steps {
                liquibaseUpdate changeLogFile: 'src/main/script/changelog-master.xml', databaseEngine: 'MySQL'
                }
            }
     }
}
