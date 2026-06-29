pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage('Clone'){
            steps{
                git 'https://github.com/abjeet16/int1.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Build docker Image'){
            steps{
                sh 'docker build -t java-demo .'
            }
        }
        stage('Deploy'){
            steps{
                sh 'docker stack deploy -c swarm.yml javastack'
            }
        }
    }
}