pipeline {
    agent { 
        node {
            stage('Update') {
                liquibaseUpdate changeLogFile: 'src/main/script/changelog-master.xml', url: 'jdbc:mysql://localhost:3306/liquibase/default?useSSL=false', credentialsId: 'mysql_default', databaseEngine: 'MySQL'
            }
        }
 
    }
}
