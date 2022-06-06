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
		
	        

                stage('Build'){
                steps{
                    script{
                        sh "ansible-playbook angular-tour-of-heroes/ansible/build.yml -i angular-tour-of-heroes/ansible/inventory/host.yml"
                    }
                }
            }	
               stage('docker') {
                steps{
                    script{
                        sh "ansible-playbook angular-tour-of-heroes/ansible/docker.yml -i angular-tour-of-heroes/ansible/inventory/host.yml"
                    }
                }
            }
            stage('docker-registry') {
                steps{
                    script{
                        sh "ansible-playbook angular-tour-of-heroes/ansible/docker-registry.yml -i angular-tour-of-heroes/ansible/inventory/host.yml"
                    }
                }
            }
}
}
