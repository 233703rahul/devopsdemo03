

node {
   stage('Checkout') {
      // Checkout the source code from a git repository
      git url: 'https://github.com/example/project.git', branch: 'master'
   }

   stage('Build') {
      // Perform an AWS CLI command to set up the build environment
      sh 'aws s3 cp s3://my-bucket/config.json config.json'
      // Build the project
      sh 'make all'
   }

   stage('Test') {
      // Perform an AWS CLI command to set up the test environment
      sh 'aws s3 cp s3://my-bucket/test-data.json test-data.json'
      // Run tests
      sh 'make test'
   }

   stage('Deploy') {
      // Perform an AWS CLI command to deploy the application
      sh 'aws s3 cp