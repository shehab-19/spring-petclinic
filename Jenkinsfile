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
              
        stage('Deployment') {

          steps {
                sshPublisher(publishers: [
                    sshPublisherDesc(
                        configName: 'server2',
                        transfers: [
                            sshTransfer(
                                sourceFiles: 'shehab.py',
                                remoteDirectory: '/home/user2',
                                removePrefix: '',
                                execCommand: '''
                                    ls -l /home/user2;
                                    python3 /home/user2/shehab.py;
                                ''',
                                execTimeout: 120000
                            )
                        ],
                        usePromotionTimestamp: false,
                        verbose: true
                    )
                ])
            }




            
            // steps {
            //     sshPublisher(publishers: [
            //         sshPublisherDesc(
            //             configName: 'server2', // The SSH server configured in Jenkins
            //             transfers: [
            //                 sshTransfer(
            //                     execCommand: 'rm /home/user2/shehab.py',
            //                     sourceFiles: 'shehab.py', // Path to the file you want to copy
            //                     remoteDirectory: '/home/user2', // Remote destination directory
            //                     removePrefix: '', // Optional: remove prefix before uploading
            //                     execCommand: '', // Optional: any command to execute after transfer
            //                     execCommand: 'python3 /home/user2/shehab.py',
            //                     execTimeout: 120000
            //                 )
            //             ],
            //             usePromotionTimestamp: false,
            //             verbose: true
            //         )
            //     ])
            // }
        }
    }
}
