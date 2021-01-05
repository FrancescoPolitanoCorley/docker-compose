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
                script{
                    build job: 'wordpress-build', parameters: [[$class: 'StringParameterValue', name: 'NAME', value: 'wordpress-image']]
                }
            }
        }
        stage ("deploy"){
            agent { 
                label 'master'  
            }
            steps{
                script{
                    build job: 'wordpress-deploy', parameters: [[$class: 'StringParameterValue', name: 'NAME', value: 'wordpress-image']]
                }
            }
        }
    }
}
