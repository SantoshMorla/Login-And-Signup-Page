pipeline{
        agent {label 'dev-agent'}
        stages{
            stage('Code'){
                steps{
                    git url: 'https://github.com/SantoshMorla/Login-And-Signup-Page.git' 
                }
            }
            stage('build'){
                when{
                    branch: 'master'
                }
                steps{
                    sh 'docker build -t login:latest .'
                }
                post{
                    echo 'Successfully build'
                }    
            }
            stage('deploy'){
                steps{
                    sh 'docker-compose down && docker-compose up'
                }

            }

        }
    }
