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
        environment {
            PLATFORM = "${PLATFORM}"
            BROWSER = "${BROWSER}"
        }
        stages {
            stage('Build') {
                steps {
                    script {
                        echo "Building on Platform: ${PLATFORM} with Browser: ${BROWSER}"
                    }
                }
            }
            stage('Test') {
                steps {
                    sh './simple_script.sh'
                }
            }
            stage('Deploy') {
                steps {
                    script {
                        echo "Deploying on Platform: ${PLATFORM} with Browser: ${BROWSER}"
                    }
                }
            }
        }
    }
}
