pipeline {
    agent any

    environment {
        JAVA_HOME = "/usr/lib/jvm/java-17-amazon-corretto"
        MAVEN_HOME = "/opt/maven"
    }

    triggers {
        githubPush()
    }

    stages {
        stage('Build') {
            steps {
                sh "${MAVEN_HOME}/bin/mvn clean package"
            }
        }

        stage('Test') {
            steps {
                sh "${MAVEN_HOME}/bin/mvn test"
            }
        }
    }
}

