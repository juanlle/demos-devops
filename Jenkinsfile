pipeline{
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
                    echo ${MAVEN_HOME}
                    echo "PATH = ${PATH}"
                    echo "JAVA_HOME = ${JAVA_HOME}"
                    echo "JENKINS_VERSION = ${JENKINS_VERSION}"
                ''' 
            }
        }
        stage("Compile") {
            steps {
                sh "echo Hemos compilado"
            }
        }
        stage("Unit test") {
            steps {
                mkdir
                sh "echo Hemos testeando"
            }
        }
       
        stage("Build") {
            steps {
                sh "echo Hemos montado imagen docker"
            }
        }
        stage("Deploy") {
            steps {
                sh "echo Hemos desplegado contendor"
            }
        }
    }
}
