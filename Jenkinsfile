node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/tmdwnsdl/web_count_jenkins.git'
    }

    stage('Build image') {
       dockerImage = docker.build("seungjjun/web_count:v1.0", "--no-cache .")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
