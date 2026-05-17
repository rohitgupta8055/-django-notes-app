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

        stage("code clone"){
            steps{
                echo "This is cloning the code!!!!"
                git url : "https://github.com/rohitgupta8055/-django-notes-app.git", branch : "main"
                echo "Code clonning Successful!!!!!!!!

            }
        }
        // stage("Code clone"){
        //     steps{
        //         sh "whoami"
        //     clone("https://github.com/LondheShubham153/django-notes-app.git","main")
        //     }
        // }
        // stage("Code Build"){
        //     steps{
        //     dockerbuild("notes-app","latest")
        //     }
        // }
        // stage("Push to DockerHub"){
        //     steps{
        //         dockerpush("dockerHubCreds","notes-app","latest")
        //     }
        // }
        // stage("Deploy"){
        //     steps{
        //         deploy()
        //     }
        // }
        
    }
}
