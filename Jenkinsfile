pipeline {
    agent { 
        node {
             label 'master' 
        }
    }
    stages{
            stage('Checkout') {
                steps {
                    git url: 'https://github.com/adeomobs/liquibase-maven.git', credentialsId: 'thegit_main_log', branch: 'master'
                }
            }
            stage('Update') {
                steps {
                    mvn --file pom.xml liquibase:update -Dliquibase.changeLogFile=src/main/script/changelog-master.xml -Dliquibase.propertyFile=src/main/resources/liquibase.properties
                }
            }
     }
}
