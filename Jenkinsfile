pipeline {
    agent any
    matrix {
        axes {
            axis {
                name 'PLATFORM'
                values 'Linux', 'Windows'
            }
            axis {
                name 'BROWSER'
                values 'Chrome', 'Firefox'
            }
        }
        stages {
            stage('Build') {
                steps {
                    script {
                        echo "Building on ${PLATFORM} with ${BROWSER}"
                    }
                }
            }
            stage('Test') {
                steps {
                    script {
                        sh './simple_script.sh'
                    }
                }
            }
            stage('Deploy') {
                steps {
                    script {
                        echo "Deploying on ${PLATFORM} with ${BROWSER}"
                    }
                }
            }
        }
    }
}
