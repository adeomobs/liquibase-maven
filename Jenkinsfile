pipeline {
    agent { node {}
    }
    stages{
            stage('Update') {
                steps {
                liquibaseUpdate changeLogFile: 'src/main/script/changelog-master.xml', databaseEngine: 'MySQL'
                }
            }
     }
}
