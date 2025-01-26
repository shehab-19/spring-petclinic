pipeline {
    agent any

    stages {
        // stage('Source') {
        //     steps {
        //         echo 'Cloning repository...'
        //         git url: 'https://github.com/spring-projects/spring-petclinic.git', branch: 'main'
        //     }
        // }

        stage('Testing') {
            steps {
                sh 'mvn'
            }
        }

        stage('Test') {
            steps {
                echo 'Test'
            }
        }
    }
}
