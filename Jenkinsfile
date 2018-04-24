properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/buhr3940/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
    }

stage ("GetInstances") {

     sh "aws ec2 describe-instances --region us-east-1"
}

stage ("CreateInstance") {
    sh "aws ec2 run-instances --image-id ami-467ca739 --count 1 --instance-type t2.micro --key-name classroom --security-group-ids sg-6b81f922- --subnet-id subnet-d3e94199 --region us-east-1"
    }
}
