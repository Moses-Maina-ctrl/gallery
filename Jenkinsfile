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
            stage("Deploy"){
                steps{
                    sh 'node server &'
                }
            }
            
        }
                    
    
}