pipeline{
    agent any
    tools{
        nodejs 'node'
    }
        stages{
            stage("Clone Code"){
                steps{
                    git branch:'master', url:'https://github.com/Moses-Maina-ctrl/gallery.git'
                }
            }
            stage("Build"){
                steps{
                    sh 'npm install'
                }
                
            }
            stage("Test"){
                steps{
                    sh 'npm install -g mocha'
                    sh 'npm test'
                }
            }
            stage("Deploy"){
                steps{
                    sh 'node server &'
                }
                post{
                    success{
                        slackSend(color: 'good',  message: "Build ID: ${env.BUILD_ID}, Build was Successful!!! YAAAY!!! See it here:https://gallery-148o.onrender.com/  ")
                    }
                }
            }
            
        }
                    
    
}