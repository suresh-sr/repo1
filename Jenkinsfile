pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                retry(3) {
                sh 'echo "Hello World"\n'
		sh 'mvn -B -DskipTests clean package'
                }
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}
