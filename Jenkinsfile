    pipeline{
            agent {label 'batch3-agent'}
            stages{
                stage('Code'){
                    steps{
                        git url: 'https://github.com/SantoshMorla/Login-And-Signup-Page.git',branch: 'master'   
                    }
                }
                stage('build'){
                    // when{
                    //     allOf{
                             
                    //     }
                        
                    // }
                    steps{
                        sh 'docker build -t login:latest .'
                    }
                    post{
                        success{
                            echo 'Successfully build'
                        }
                        
                    }    
                }
                stage('deploy'){
                    steps{
                        sh 'docker-compose down && docker-compose up'
                    }

                }

            }
        }
