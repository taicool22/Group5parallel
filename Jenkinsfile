pipeline{
    agent any
    stages{
        stage('1-repoClone'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/taicool22/taicool-pipeline-demo.git']]])
            }
        }
        Parallel{
            stage('1-identification'){
                steps{
                    sh 'whoami'
                }
            }
            stage('2-file creation'){
                step{
                    sh 'touch "taiwo.txt"'
                    sh 'cat "my name is taiwo" > taiwo.txt'
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