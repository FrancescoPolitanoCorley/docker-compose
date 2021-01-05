pipeline{
    parameters {
        string(name: 'NAME', defaultValue: 'my_docker_image')
    }
    agent none
    stages{
        stage ("build"){
            agent { 
                label 'master'  
            }
            steps{
             sh ("docker build -t ${params.NAME} .")
            }
        }
        stage ("deploy"){
            agent { 
                label 'master'  
            }
            steps{
             sh("docker-compose up -d)")
            }
        }
    }
}
int returnZero(){
    return 0
}