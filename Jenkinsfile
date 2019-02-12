pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    environment {
            JARNAME = 'test'
        }

    stages {
        stage('Build') { 
            steps {
                sh 'mvn jar:jar -Djar.finalName=custom-jar-name'
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
