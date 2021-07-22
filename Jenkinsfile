#!/usr/bin/env groovy
node('master') {
    checkout scm
    docker.withRegistry('', 'dockerhub-creds'){

        stage('11.2') {
            def image = docker.build("familyresearchcouncil/oracle", './11.2')

            if( env.BRANCH_NAME == 'master' ){
                image.push()
                image.push('11.2')
            }
        }
    }
}
