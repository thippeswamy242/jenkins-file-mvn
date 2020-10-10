pipeline {
    agent none
    stages {
        stage('Build-1') {
            agent any
            steps {
                checkout scm
                sh 'hostname -i'
                 
            }
        }
        stage('Test on Slave-1') {
            agent { 
                label 'slave-1'
            }
            steps {
              //  sh 'sudo mkdir /root/demo4'
              //  sh 'hostname -i'
              //  sh 'sudo rm -rf /root/demo'
              //  sh 'sudo rm -rf /root/demo1'
                sh 'sudo rm -rf /home/ec2-user/newdirectory'
                sh 'sudo rm -rf *;sudo git clone https://github.com/thippeswamy242/hello-world.git /home/ec2-user/newdirectory'
           
            
            }
        }
        
        stage('Build') {
           agent { 
               label 'slave-2'
           }
            steps {
                sh 'sudo mkdir /root/demo'
                sh 'hostname -i'
            
            }
        }
    }
    
}
