pipeline {
    agent { 
        node {
             label 'my-maven test' 
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
