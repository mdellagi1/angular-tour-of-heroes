pipeline {
    agent any
        stages {
            stage('Pull') {
                steps{
                    script{
                        checkout([$class: 'GitSCM',
                        branches: [[name: '*/main']],
                            userRemoteConfigs: [[
                                credentialsId: 'cOqBvcxf8oPTJYPXg4HXaoTAMLdSNL3NyVCh',
                                url: 'https://github.com/mdellagi1/angular-tour-of-heroes.git'
                            ]]])
                    }
                }
            }
            stage('Build') {
                steps{
                    script{
                        sh "ansible-playbook Myapp/ansible/build.yml -i Myapp/ansible/inventory/host.yml"
                    }
                }
            }
            stage('docker') {
                steps{
                    script{
                        sh "ansible-playbook Myapp/ansible/docker.yml -i Myapp/ansible/inventory/host.yml"
                    }
                }
            }
            stage('docker-registry') {
                steps{
                    script{
                        sh "ansible-playbook Myapp/ansible/docker-registry.yml -i Myapp/ansible/inventory/host.yml"
                    }
                }
            }
        }
}
