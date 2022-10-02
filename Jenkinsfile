pipeline {
    agent any {
        stages {
            stage ("Clean all old files exist"){
                steps {
                    deleteDir()
                }
            }
            stage ("Clone the apps from Git"){
                steps {
                    sh "git clone https://github.com/jenkins-docs/simple-java-maven-app.git"
                }
            }
            stage ( "Build the app"){
                steps{
                    dir("simple-java-maven-app"){
                        sh "mvn clean install"
                    }
                }
            }
            stage{
                steps("Testing the App"){
                    steps{
                        dir("simple-java-maven-app"){
                            sh "mvn test"
                        }
                    }
                }
            }
        }
    }


}