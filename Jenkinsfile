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
                    mvn --file pom.xml liquibase:update -Dliquibase.propertyFile=src/main/resources/liquibase.properties
                }
            }
     }
}
