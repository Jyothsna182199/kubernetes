node {
    stage("Checkout the code from Github"){
        git branch: 'main', credentialsId: '6a81a68c-ee7a-48ee-8637-e20a2ee0ff34', url: 'https://github.com/Jyothsna182199/kubernetes.git'
    }
    stage("Sending Docker file to ansible server over SSH"){
        sshagent(['test-mini server private key']) {
            sh 'ssh -o StrictHostKeyChecking=no -vvv -i /home/ubuntu/.ssh/id_rsa.pub ubuntu@20.55.252.21' 
            sh 'scp /var/lib/jenkins/workspace/pipeline/Dockerfile ubuntu@20.55.252.21:/home/ubuntu'
            sh 'echo File transfered successfully'
        }
    }
}
