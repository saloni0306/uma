pipeline {
    agent any

    stages {
        stage('continuous down') {
            steps {
               git 'https://github.com/AneesRavidKhan/gamutkart.git' 
            }
        }
        stage('continuous build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('continuous deploy') {
            steps {
                sh 'sshpass -p "saloni" scp target/gamutkart.war saloni@172.17.0.3:/opt/apache-tomcat-9.0.56/webapps'
            }
        }
    }
}
