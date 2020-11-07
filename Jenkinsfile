pipeline {
    agent {
        label'master'
    }
    parameters {
        string(name: 'stack_name', defaultValue: 'joel-demo', description: 'CFT stack Name',)
        choice(name: 'aws_region', choices: ['us-east-1', 'us-east-2', ''], description: 'AWS region to deploy joel CFT',)
        choice(name: 'stack_state', choices: ['create_stack', 'update_stack', 'delete_stack'], description: 'joel clutser stack state',)
        choice(name: 'slack_notify', choices: ['create_joel_cluster', 'update_joel_cluster', 'delete_joel_cluster'], description: 'joel clutser stack state',)        
        choice(name: 'stack_status', choices: ['CREATE_IN_PROGRESS', 'UPDATE_IN_PROGRESS', 'DELETE_IN_PROGRESS'], description: 'OpenShift cluster create,update or delete status',) 
    }
    stages {
        stage('clone joel git repo') {
            steps {
                git branch: 'joel-demo',
                    credentialsId: 'github-cicd',
                        url: 'https://github.com/oscarose/joel-demo.git'
            }
        }
        stage('run shell commands') {
            steps {
                script {
                    sh """
                    mkdir -p /root/joel/joel1/joel3
                    ansible --version
                    df -h
                    """
                }
            }
        }
    }
}

