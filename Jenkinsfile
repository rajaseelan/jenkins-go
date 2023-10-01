node {
    stage('SCM') {
        echo 'Gathering code from version control'
        git branch: '${branch}', url: 'https://github.com/rajaseelan/jenkins-go.git'
    }
    stage('Build') {
        echo "Building Go App"
        sh 'go version'
        sh 'go build -o main -a main.go'
        releasenotes(changes: "false");
    }

    stage('Gonna Fail') {
        try {
            echo 'THis will fail'
            sh 'go not-a-command'
        } catch(ex) {
            echo 'Something Went wrong'
            echo ex.toString()
            //currentBuild.result = 'FAILURE'
        } finally {
            echo "In Finally, everything's gonna be ok"
        }
    }

    stage('Run App') {
        echo 'Running app...'
        sh './main'
    }

    stage('Delete artifact') {
        echo 'Deleting artifact'
        sh 'rm -vf main'
    }
}