pipeline {
	    agent any

	        //Orchestrator Services
	        UIPATH_ORCH_URL = "https://cloud.uipath.com/"
	        UIPATH_ORCH_LOGICAL_NAME = "nikita"
	        UIPATH_ORCH_TENANT_NAME = "nikita"
	        UIPATH_ORCH_FOLDER_NAME = "IT"
	    }
	

	    stages {
	    
	    	// Deploy Stages
	        stage('Deploy Tests') {
	            steps {
	                echo 'Deploying ${main} to orchestrator'
	                UiPathDeploy (
	                packagePath: "Output\\Tests\${env.1.0.114420490}",
	                orchestratorAddress: '${https://cloud.uipath.com/ssstkwxnjg/nikita/orchestrator_/}',
	                orchestratorTenant: "${nikita}",
	                folderName: "${IT}",
	                environments: 'INT',
	                credentials: Token(accountName: "${nikita}", credentialsId: 'YySkJ9PwEoXhl32OqKGBjwM5jiX7DKiHLYFnK6zeL6HNF'),
					traceLevel: 'None',
					entryPointPaths: 'TestCase1.xaml')
	            	}
			}
	    		}
	
	    post {
	        success {
	            echo 'Deployment has been completed!'
	        }
	        failure {
	          echo "FAILED: Job '${env.JOB_NAME} [${env.1.0.114420490}]' (${env.JOB_DISPLAY_URL})"
	        }
	        always {
	            /* Clean workspace if success */
	            cleanWs()
	        }
	    }
	
