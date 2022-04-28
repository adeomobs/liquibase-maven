pipeline {
    agent any
    tools {
        maven 'Maven 3.3.9'
        jdk 'jdk8'
    }
    stages{
            stage ('Build') {
                steps {
                    sh 'mvn -Dmaven.test.failure.ignore=true install' 
                }
            }
            stage('Checkout') {
                steps {
                    git url: 'https://github.com/adeomobs/liquibase-maven.git', credentialsId: 'thegit_main_log', branch: 'master'
                }
            }
            stage('Update') {
                steps {
                    sh 'mvn --file pom.xml liquibase:update -Dliquibase.changeLogFile=src/main/script/changelog-master.xml -Dliquibase.propertyFile=src/main/resources/liquibase.properties'
                }
            }
     }
}
