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
                script {
                    // Example: Copy a file to the remote server
                    publishOverSSH(
                        server: 'server2', // Name of your configured SSH server
                        transfers: [
                            [
                                source: 'shehab.py',  // Path to the file you want to copy
                                remote: '/home/user2'  // Remote destination directory
                            ]
                        ]
                    )
                }
            }


            // steps {
            //         script{
            //             publishOverSsh(
            //                 server: 'Server2', // The name of your configured server in "Publish Over SSH"
            //                 verbose: true,     // Optional: Enable detailed logs
            //                 transfers: [
            //                     sshTransfer(
            //                         sourceFiles: 'shehab.py',       // File to copy
            //                         remoteDirectory: '/home/user2' // Destination directory on the remote server
            //                     )
            //                 ]
            //             )
            // }
            // }
        }
    }
}
