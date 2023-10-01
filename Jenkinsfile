node {
    stage('SCM') {
        echo 'Gathering code from version control'
        git branch: '${branch}', url: 'https://github.com/rajaseelan/jenkins-go.git'
    }
    stage('Build') {
        echo "Building Go App"
    }

    stage('Run App') {
        echo 'Running app...'
    }

    stage('Delete artifact') {
        echo 'Deleting artifact'
    }
}