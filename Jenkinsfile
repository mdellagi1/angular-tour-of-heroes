pipeline
{
	agent any
	 stages {
		stage('Pull'){
		 steps{
	          	script{
		           checkout([$class: 'GITSCM', branches: [[name: '/master']],
	                         	userRemoteConfigs: [[
						credentialsId:'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',
			                        url:'https://github.com/mdellagi1/angular-tour-of-heroes.git'
			]]
			])
		              }	
		      }
		}
		
	        }

            stage('Build') {
                steps{
                    script{
                        sh "ansible-playbook angular-tour-of-heroes/ansible/build.yml -i angular-tour-of-heroes/ansible/inventory/host.yml"
                    }
                }
            }	
=======
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
>>>>>>> 2be73dc0206e7b32d98c7c9dec84b96bd0a9b2eb
}
