pipeline{
    parameters {
        string(name: 'NAME', defaultValue: 'wordpress-image')
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
             step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: false])
            }
        }
    }
}
int returnZero(){
    return 0
}