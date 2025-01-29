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
                script{
                    // First SSH Publisher step
                    sshPublisher(publishers: [
                        sshPublisherDesc(
                            configName: 'server2', 
                            transfers: [
                                sshTransfer(
                                    cleanRemote: false, 
                                    excludes: '',  
                                    execTimeout: 120000, 
                                    flatten: false, 
                                    makeEmptyDirs: false, 
                                    noDefaultExcludes: false, 
                                    patternSeparator: '[, ]+', 
                                    remoteDirectory: '', 
                                    remoteDirectorySDF: false, 
                                    removePrefix: '',
                                    // sourceFiles: 'shehab.py',
                                    execCommand: 'rm shehab.py'
                                )
                            ],
                            usePromotionTimestamp: false,
                            verbose: true
                        )
                    ])

                    sshPublisher(publishers: [
                        sshPublisherDesc(
                            configName: 'server2', 
                            transfers: [
                                sshTransfer(
                                    cleanRemote: false, 
                                    excludes: '',  
                                    execTimeout: 120000, 
                                    flatten: false, 
                                    makeEmptyDirs: false, 
                                    noDefaultExcludes: false, 
                                    patternSeparator: '[, ]+', 
                                    remoteDirectory: '', 
                                    remoteDirectorySDF: false, 
                                    removePrefix: '',
                                    execCommand: 'ls -l && python3 shehab.py',
                                    sourceFiles: 'shehab.py'
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
}
