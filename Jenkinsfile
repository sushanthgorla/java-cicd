
node {
    stage('Checkout') {
        checkout scm
    }

    stage('Build and Test') {
        bat '"C:\\Users\\susha\\Downloads\\apache-maven-3.10.0-bin\\apache-maven-3.10.0\\bin\\mvn.cmd" package'
    }

    stage('Publish Test Results') {
        junit allowEmptyResults: true,
              testResults: 'target/surefire-reports/*.xml'
    }

    stage('Archive JAR') {
        archiveArtifacts artifacts: 'target/*.jar',
                         fingerprint: true
    }
}
