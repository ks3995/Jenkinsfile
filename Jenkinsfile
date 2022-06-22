pipeline {
    agent any
    environment{
        PATH = "/usr/share/maven/bin:$PATH"

    stages {
        stage ('Compile Stage') {
          steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh "mvn clean compile"
                }
            }
        }

        stage ('Testing Stage') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh "mvn test"
                }
            }
        }

       stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh "mvn deploy"
                }
            }
        }
    }
}
