pipeline {
    agent any
    
    stages {
        // stage('Build') {
        //     steps {
        //         checkout([$class: 'GitSCM', branches: [[name: '*/development'], [name: '*/qa']], extensions: [], userRemoteConfigs: [[credentialsId: 'jenkins', url: 'https://github.com/arunnetha/react.git']]])
        //         sh 'echo build'
        //     }
        // }

        stage('devbuild') {
            when {
                beforeAgent true
                branch 'development'
                expression {
                    return env.CHANGE_ID != null
                }
            }
            steps {
                sh 'echo devbuild'
            }
        }
        stage('qabuild') {
            when {
                beforeAgent true
                branch 'qa'
                expression {
                    return env.CHANGE_ID != null
                }
            }
            steps {
                sh 'echo qabuild'
            }
        }
        
    }
    
}
