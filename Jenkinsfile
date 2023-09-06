pipeline {
  agent any
  
  stages {
        stage('Build') {
      steps {
        echo "Fetch the source code from the directory path ${env.DIRECTORY_PATH}"
        echo "Compile the code and generate any necessary artifacts"
      }
    }
    
    stage('Test') {
      steps {
        echo "Unit tests"
        echo "Integration tests"
      }
    }
    
    stage('Code Quality Check') {
      steps {
        echo "Checking the quality of the code"
      }
    }
    
    stage('Deploy') {
      steps {
        echo "Deploying the application to ${env.TESTING_ENVIRONMENT} environment"
       
      }
    }
    stage('Approval') {
      steps {
        sleep 10
      }
    }
    
    
    
    stage('Deploy to Production') {
      steps {
        echo "Deploying the code to the ${env.PRODUCTION_ENVIRONMENT} environment"
      }
       }
  }
  post {
    success {
      emailext body: 'The pipeline has completed successfully.',
        subject: 'Pipeline success',
        to: 'isivakumardevika028@gmail.com'
    }
  }
}
