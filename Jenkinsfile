// pipeline {
// 	    agent any

// 	        //Orchestrator Services
// 	        UIPATH_ORCH_URL = "https://cloud.uipath.com/"
// 	        UIPATH_ORCH_LOGICAL_NAME = "nikita"
// 	        UIPATH_ORCH_TENANT_NAME = "nikita"
// 	        UIPATH_ORCH_FOLDER_NAME = "IT"
// 	    }
	

// 	    stages {
	    
// 	    	// Deploy Stages
// 	        stage('Deploy Tests') {
// 	            steps {
// 	                echo 'Deploying ${main} to orchestrator'
// 	                UiPathDeploy (
// 	                packagePath: "Output\\Tests\${env.1.0.114420490}",
// 	                orchestratorAddress: '${https://cloud.uipath.com/ssstkwxnjg/nikita/orchestrator_/}',
// 	                orchestratorTenant: "${nikita}",
// 	                folderName: "${IT}",
// 	                environments: 'INT',
// 	                credentials: Token(accountName: "${nikita}", credentialsId: 'YySkJ9PwEoXhl32OqKGBjwM5jiX7DKiHLYFnK6zeL6HNF'),
// 					traceLevel: 'None',
// 					entryPointPaths: 'TestCase1.xaml')
// 	            	}
// 			}
// 	    		}
	
// 	    post {
// 	        success {
// 	            echo 'Deployment has been completed!'
// 	        }
// 	        failure {
// 	          echo "FAILED: Job '${env.JOB_NAME} [${env.1.0.114420490}]' (${env.JOB_DISPLAY_URL})"
// 	        }
// 	        always {
// 	            /* Clean workspace if success */
// 	            cleanWs()
// 	        }
// 	    }
	

pipeline {
 agent any

    	        // Environment Variables
	        environment {
	        MAJOR = '1'
	        MINOR = '0'
	        //Orchestrator Services
	        UIPATH_ORCH_URL = "https://cloud.uipath.com/"
	        UIPATH_ORCH_LOGICAL_NAME = "nikita"
	        UIPATH_ORCH_TENANT_NAME = "nikita"
	        UIPATH_ORCH_FOLDER_NAME = "IT"
	    }
	

	    stages {
	

	        // Printing Basic Information
	        stage('Preparing'){
	            steps {
	                echo "Jenkins Home ${env.JENKINS_HOME}"
	                echo 'Jenkins URL ${env.http://localhost:8080/job/Testing/configure}'
	                echo "Jenkins JOB Number ${env.7}"
	                echo "Jenkins JOB Name ${env.testing}"
	                echo "GitHub BranhName ${env.main}"
	                checkout scm
	

	            }
	        }
	

	         // Build Stages
	        stage('Build') {
	            steps {
	                echo "Building..with ${WORKSPACE}"
	                UiPathPack (
                      outputPath: "Output\\${env.1.0.114420490}",
                      projectJsonPath: "project.json",
                      version: [$class: 'ManualVersionEntry', version: "${MAJOR}.${MINOR}.${env.1.0.114420490}"],
                      useOrchestrator: true,
					  traceLevel: 'None'
        )
	            }
	        }
	         // Test Stages
	        stage('Test') {
	            steps {
	                echo 'Testing..the workflow...'
	            }
	        }
	

	         // Deploy Stages
	        stage('Deploy to UAT') {
	            steps {
	                echo "Deploying ${main} to UAT "
                UiPathDeploy (
                packagePath: "Output\\${env.1.0.114420490}",
                orchestratorAddress: '${https://cloud.uipath.com/ssstkwxnjg/nikita/orchestrator_}',
                orchestratorTenant: "${nikita}",
                folderName: "${IT}",
//                 environments: 'DEV',
                //credentials: [$class: 'UserPassAuthenticationEntry', credentialsId: 'APIUserKey']
                credentials: Token(accountName: "${nikita}", credentialsId: 'MGUC531S9667tDKUAuHeqZxpbXKYdViAL4OMKZVLrCRbK'), 
				traceLevel: 'None',
				entryPointPaths: 'TestCase1.xaml'
	

	        )
	            }
	        }
	

	

	         // Deploy to Production Step
	        stage('Deploy to Production') {
	            steps {
	                echo 'Deploy to Production'
	                }
	            }
	    }
	

	    // Options
	    options {
	        // Timeout for pipeline
	        timeout(time:80, unit:'MINUTES')
	        skipDefaultCheckout()
	    }
	

	

	    // 
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
	

	}

