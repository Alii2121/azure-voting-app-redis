/* groovylint-disable BlockEndsWithBlankLine, CompileStatic, FileEndsWithoutNewline */
pipeline {
    agent any
stages {
    stage ('Verify Branch') {
        steps {
        echo '$GIT_BRANCH'
        } 
    }
stage ("DOCKER BUILD") {
steps {
    cmd(script: 'docker images -a')
    cmd(script:"""
    cd azure-vote/
    docker images -a
    docker build -t jenkins-pipeline .
    docker images -a
    cd ..
 """ )
}
}

}
}

