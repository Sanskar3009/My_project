pipeline {
    agent any

    environment {
        // Explicitly set Java 17 for builds
        JAVA_HOME = "/usr/lib/jvm/java-17-openjdk-amd64"
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Sanskar3009/My_project.git'
            }
        }

        stage('Backend Build') {
            steps {
                dir ('backend') {
                
                    sh "java -version"   // confirm Java 17
                    // If Maven
                    sh "mvn clean install"
                    // Or if Gradle
                    // sh "./gradlew build"
                }
            }
        }

        stage('Frontend Build') {
            steps {
                dir ('frontend') {
                    sh "java -version"   // confirm Java 17
                    // If frontend is Java-based (Spring Boot, etc.)
                    sh "mvn clean install"
                    // Or Gradle
                    // sh "./gradlew build"
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying frontend and backend..."
                // Example run commands
                // sh "java -jar backend/target/backend.jar &"
                // sh "java -jar frontend/target/frontend.jar &"
            }
        }
    }
}
