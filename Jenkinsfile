pipeline{
    agent {label '9dec2e08431f '}
    stages{
        stage('Printing hostname') {
            steps {
                sh 'hostname'
                sh 'hostname -i'
            }
        }
        stage('build') {
            steps{
		withMaven(maven: 'mvn-3.5.4')
                sh 'mvn clean install'
            }
        }
    }
}
