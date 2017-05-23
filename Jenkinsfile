pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                def mvnHome = tool 'M3'
                sh "${mvnHome}/bin/mvn -B -Dmaven.test.failure.ignore verify"
                step([$class: 'JUnitResultArchiver', testResults:
                '**/target/foobar/TEST-*.xml'])
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
