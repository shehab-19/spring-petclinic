pipeline {
    agent any

    // tools {
    //     maven 'maven' // Uncomment if you need Maven installed
    // }

    // parameters {
    //     choice(
    //         name: 'MAVEN_COMMAND',
    //         choices: ['install', 'package', 'clean', 'test'],
    //         description: 'Select the Maven command to execute'
    //     )
    // }

    stages {
        // stage('Source') {
        //     steps {
        //         echo 'Cloning repository...'
        //         git url: 'https://github.com/spring-projects/spring-petclinic.git', branch: 'main'
        //     }
        // }

        // stage('Maven Command') {
        //     steps {
        //         sh "mvn ${params.MAVEN_COMMAND}"
        //     }
        // }        

        stage('Deployment') {
            steps {
                publishOverSsh(
                    server: 'Server2', // The name of your configured server in "Publish Over SSH"
                    verbose: true,     // Optional: Enable detailed logs
                    transfers: [
                        sshTransfer(
                            sourceFiles: 'shehab.py',       // File to copy
                            remoteDirectory: '/home/user0' // Destination directory on the remote server
                        )
                    ]
                )
            }
        }
    }
}
