pipeline {
    agent any
    environment {
	aws_access_key_id = credentials('jenkins-aws-secret-key-id')
      }
    stages {
        stage('Build') {
            steps {
                retry(3) {
                sh 'echo "Hello World"\n'
		sh 'mvn -B -DskipTests clean package'
		sh 'echo "$aws_access_key_id"'
                }
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}
