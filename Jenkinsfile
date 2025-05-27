pipeline {
    agent any

    stages {
        stage('Initialize') {
            steps {
                script {
                    def currentBranch = env.BRANCH_NAME ?: 'main'
                    env.CONFIG_NAME = currentBranch == 'production' 
                                      ? 'Vizo-prod' 
                                      : (currentBranch == 'main' 
                                          ? 'Aksum' 
                                          : 'UNKNOWN')
                }
            }
        }

        stage('Print Config Name') {
            steps {
                echo "🔧 Branch: ${env.BRANCH_NAME}"
                echo "📦 Config Name: ${env.CONFIG_NAME}"
            }
        }
    }
}
