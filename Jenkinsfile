pipeline {
    agent { 
        node {
             label 'master' 
        }
    }
    stages{
            stage('Update') {
                steps {
                liquibaseUpdate changeLogFile: 'src/main/script/changelog-master.xml', databaseEngine: 'MySQL'
                }
            }
     }
}
