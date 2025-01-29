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
                                cleanRemote: false, 
                                excludes: '',  
                                execTimeout: 120000, 
                                flatten: false, 
                                makeEmptyDirs: false, 
                                noDefaultExcludes: false, 
                                patternSeparator: '[, ]+', 
                                remoteDirectory: '/home/user2', 
                                remoteDirectorySDF: false, 
                                removePrefix: '',
                                execCommand: 'ls -l /home/user2',
                            )
                        ],
                        usePromotionTimestamp: false,
                        verbose: true
                    )
                ])
            }          
        }
    }
}
