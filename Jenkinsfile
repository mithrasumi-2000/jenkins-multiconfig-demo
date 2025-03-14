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
                    withEnv(["PLATFORM=${PLATFORM}", "BROWSER=${BROWSER}"]) {
                        echo "Building on Platform: ${PLATFORM} with Browser: ${BROWSER}"
                    }
                }
            }
            stage('Test') {
                steps {
                    withEnv(["PLATFORM=${PLATFORM}", "BROWSER=${BROWSER}"]) {
                        sh './simple_script.sh'
                    }
                }
            }
            stage('Deploy') {
                steps {
                    withEnv(["PLATFORM=${PLATFORM}", "BROWSER=${BROWSER}"]) {
                        echo "Deploying on Platform: ${PLATFORM} with Browser: ${BROWSER}"
                    }
                }
            }
        }
    }
}
