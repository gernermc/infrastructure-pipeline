properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/gernermc/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"    
    }
    stage ("GetInstances") {
        sh "aws ec2 describe-instances --region us-east-1"
    }
    stage ("CreateInstance") {
        sh "aws ec2 run-instances --image-id ami-013be31976ca2c322 --count 1 --instance-type t2.micro --key-name gernerskeypair --security-group-ids sg-06cdd01827d8b28b0 --subnet-id subnet-366ceb51 --region us-east-1"
    }
}
