pipeline{
    agent any
    stages{
        stage('1-repoClone'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/taicool22/taicool-pipeline-demo.git']]])
            }
        }
        stage('2-parallel job'){
            parallel{
                stage('1-identification'){
                    step{
                        sh 'whoami'
                    }
                }
                stage('2-file creation'){
                    step{
                        sh 'cat "my name is taiwo" > taiwo.txt '
                    }
                }
            }
        }
        stage('2-cpuAnalysis'){
            steps{
                sh 'lscpu'
            }
        }
        stage('3-memoryCheck'){
            steps{
                sh 'free -g'
            }
        } 
        stage('4-os-stats'){
            steps{
                sh 'cat /etc/os-release'
            }
        }   
    }
    
    
}