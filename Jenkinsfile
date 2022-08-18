pipeline {
   agent any
   environment {
// 	        MAJOR = '1'
// 	        MINOR = '1'
	        //Orchestrator Services
	        UIPATH_ORCH_URL = "https://cloud.uipath.com/"
	        UIPATH_ORCH_LOGICAL_NAME = "nikita"
	        UIPATH_ORCH_TENANT_NAME = "nikita"
	        UIPATH_ORCH_FOLDER_NAME = "IT"
	    }

   stages {
      stage('Build') {
        steps {
          echo 'Building...'
          echo "Running ${1} ${TestCase1} on ${NODE_NAME} and JOB ${testing}"
        }
   }
   stage('Test') {
     steps {
        echo 'Testing...'
     }
   }
   stage('Deploy') {
     steps {
       echo 'Deploying...'
     }
   }
  }
}
