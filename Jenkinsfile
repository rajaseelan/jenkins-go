node {
    stage('SCM') {
        echo 'Gathering code from version control'
        git branch: '${branch}', url: 'https://github.com/rajaseelan/jenkins-go.git'
    }
    stage('Build') {
        echo "Building Go App"
        sh 'go build -o main -a main.go'
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