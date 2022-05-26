pipeline {
    agent any
    triggers { // Sondear repositorio a intervalos regulares
        pollSCM('* * * * *')
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    pwd
                    ls
                    echo $MAVEN_HOME
                    echo "PATH = ${PATH}"
                    echo "JAVA_HOME = ${JAVA_HOME}"
                    echo "JENKINS_VERSION = ${JENKINS_VERSION}"
                ''' 
            }
        }
        stage("Compile") {
            steps {
                sh "mvn compile"
            }
        }
        stage("Unit test") {
            steps {
                sh "mvn test"
            }
        }
       
        stage("Build") {
            steps {
                sh "mvn package"
            }
        }
        stage("Deploy") {
            steps {
                sh "mvn install"
            }
        }
    }
}
