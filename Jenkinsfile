pipeline {
    agent {
        node{
            label 'Agent1'
        }
    }

    environment {
        GREETINGS= 'Hello Jenkins'
    }
    options{
        timeout(time: 1, unit: 'SECONDS')
    }
    //build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh """
                    echo 'Here I wrote.... shell script'
                    echo " $GREETING"
                    """
            }
        }
    }

    // Post build
post {
    always {
        echo 'I will always say hello again'
    }
    failure {
        echo ' this runs when pipeline is failed, used generally to send some alerts'
    }
    success {
        echo 'i will say  hello  when pipeline is success'
    }

}
}

