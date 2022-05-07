pipeline {
    agent any
        stages {
            stage('Pull') {
                steps{
                    script{
                        checkout([$class: 'GitSCM',
                        branches: [[name: '*/master']],
                            userRemoteConfigs: [[
                                credentialsId: 'cOqBvcxf8oPTJYPXg4HXaoTAMLdSNL3NyVCh',
                                url: 'https://github.com/mdellagi1/angular-tour-of-heroes.git'
                            ]]])
                    }
                }
            }
        }
}
