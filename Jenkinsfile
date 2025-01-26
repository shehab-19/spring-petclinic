pipeline {
    agent any
        tools {
       maven 'maven'
    }

        parameters {
        choice(
            name: 'MAVEN_COMMAND',
            choices: ['install', 'package', 'clean', 'test'],
            description: 'Select the Maven command to execute'
        )
    }

    stages {
        // stage('Source') {
        //     steps {
        //         echo 'Cloning repository...'
        //         git url: 'https://github.com/spring-projects/spring-petclinic.git', branch: 'main'
        //     }
        // }

        stage('mvn command') {
            steps {
                sh "mvn ${params.MAVEN_COMMAND}"
            }
        }        
    }
}
