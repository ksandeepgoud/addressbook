pipeline {
    agent any

    stages {
        stage('git-clone') {
            steps {
                git 'https://github.com/ksandeepgoud/addressbook.git'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('review') {
            steps {
                sh 'mvn pmd:pmd'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('coverage') {
            steps {
                sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
            }
        }
        stage('package') {
            steps {
                sh 'mvn package'
            }
        }
        
    }
}
