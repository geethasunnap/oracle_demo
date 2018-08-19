pipeline{
    agent any 
    stages{
        stage('Printing hostname') {
            steps {
                sh 'hostname'
                sh 'hostname -i'
            }
        }
        stage('build') {
            steps{
				withMaven(maven: 'mvn-3.5.4'){
                sh 'mvn clean install'
            }
			}
        }
		stage('deploy') {
            steps{
				withMaven(maven: 'mvn-3.5.4'){
                sh 'scp /home/geetha/.m2/repository/com/jaga/oraclepractise/1.0-SNAPSHOT/oraclepractise-1.0-SNAPSHOT.war root@172.17.0.4:/home/softwares/tomcat_app_server/apache-tomcat-8.5.32/webapps/'
            }
			}
        }
    }
}
