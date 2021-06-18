pipeline {
    agent any
    stages {
        stage("clone"){
            steps{
                git credentialsId: '119f2c61-8c00-4db8-9c51-c677d3597ff9', url: 'https://github.com/Aneescalpine/wilffly2.git'
            }
        }
        stage("Build"){
            steps{
                sh "mvn clean install"
            }
        }
        stage("Deploy"){
            steps{
                sshagent(['a63e4f49-2194-4771-ba8a-2efab8f43b79']) {
                    sh "scp -o StrictHostKeyChecking=no target/SpringBootStaticWeb-0.0.1-SNAPSHOT.jar ubuntu@18.188.26.211:/opt/tomcat/webapps"
    // some block
}
            }
        }
    }
}
