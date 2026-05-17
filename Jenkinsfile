@Library('Shared')_
pipeline{
    agent { label 'rohit'}
    
    stages{
        stage("Hello Rohit Gupta!!!!"){
            steps{
                sh "whoami"
                hello()
            }
        }

     stage("Code Clone"){
        steps{
            script{

                def gitUrl = "https://github.com/rohitgupta8055/-django-notes-app.git"
                def gitBranch = "main"

                clone(gitUrl, gitBranch)
            }
        }
        }
        
        stage("Code Build"){
            steps{
                script{
                    
                    def dockerHubUser = "rohitgupta8055"
                    def projectName   = "notes-app"
                    def imageVersion  = "latest"

                    build(dockerHubUser, projectName, imageVersion)
                }
            }
        }

        // stage("Push to DockerHub"){
        //     steps{
        //         script{
        
        //             echo '''
        //             ██████╗     ██╗   ██╗    ███████╗    ██╗  ██╗
        //             ██╔══██╗    ██║   ██║    ██╔════╝    ██║  ██║
        //             ██████╔╝    ██║   ██║    ███████╗    ███████║
        //             ██╔═══╝     ██║   ██║    ╚════██║    ██╔══██║
        //             ██║          ╚██████╔╝    ███████║    ██║  ██║
        //             ╚═╝           ╚═════╝     ╚══════╝    ╚═╝  ╚═╝
        //             '''
        
        //             withCredentials([usernamePassword(
        //                 credentialsId:'dockerHubCred',
        //                 passwordVariable:'dockerHubPass',
        //                 usernameVariable:'dockerHubUser')]){
        
        //                 def imageName = "notes-app"
        //                 def imageVersion = "latest"
        
        //                 sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
        
        //                 sh "docker image tag ${imageName}:${imageVersion} ${env.dockerHubUser}/${imageName}:${imageVersion}"
        
        //                 sh "docker push ${env.dockerHubUser}/${imageName}:${imageVersion}"
        //             }
        
        //             echo '''
        //             ███████╗    ██╗   ██╗     ██████╗     ██████╗    ███████╗    ███████╗    ███████╗    ██╗   ██╗    ██╗
        //             ██╔════╝    ██║   ██║    ██╔════╝    ██╔════╝    ██╔════╝    ██╔════╝    ██╔════╝    ██║   ██║    ██║
        //             ███████╗    ██║   ██║    ██║         ██║         █████╗      ███████╗    ███████╗    ██║   ██║    ██║
        //             ╚════██║    ██║   ██║    ██║         ██║         ██╔══╝      ╚════██║    ╚════██║    ██║   ██║    ██║
        //             ███████║    ╚██████╔╝    ╚██████╗    ╚██████╗    ███████╗    ███████║    ███████║    ╚██████╔╝    ███████╗
        //             ╚══════╝     ╚═════╝      ╚═════╝     ╚═════╝    ╚══════╝    ╚══════╝    ╚══════╝     ╚═════╝     ╚══════╝
        //             '''
        //         }
        //     }
        // }

        stage("Push Docker Image"){
        
            steps{
                script{
        
                    def imageName     = "notes-app"
                    def imageTag      = "latest"
                    def dockerHubCred = "dockerHubCred"
        
                    push(dockerHubCred, imageName, imageTag)
                }
            }
        }
        
        stage("Deploy Application"){
            steps{
                deploy()
            }
        }
        
    }
}
