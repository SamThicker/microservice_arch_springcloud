pipeline {
    agent any
    environment {
      IMAGE_NAME = "ruoyi-admin"
      WS = "/"
    }

    //定义流水线的加工流程
    stages {
        //流水线的所有阶段
        stage('环境检查'){
            steps {
               sh 'pwd && ls -alh'
               sh 'printenv'
               sh 'docker version'
               sh 'java -version'
               sh 'git --version'
            }
        }

        stage("拉取代码"){
            steps{
                script {
                    echo "拉取代码"
                }
            }
        }

        stage('2.编译'){
            steps {
               sh 'pwd && ls -alh'
               sh 'mvn -v'
               //sh 'cd ${WS} && mvn clean package -Dmaven.test.skip=true'
            }
        }

        stage('3.打包'){
            steps {
               sh 'pwd && ls -alh'
               sh 'echo ${WS}'
               // sh 'mv ${WS}/${IMAGE_NAME}/target/*.jar ${WS}/${IMAGE_NAME}.jar && pwd && ls -alh && docker build -t ${IMAGE_NAME} .'
               //sh 'docker build -t ${IMAGE_NAME} -f Dockerfile ${WS}/${IMAGE_NAME}/target/'
            }
        }

        stage("项目构建"){
            steps{
                script {
                    echo "项目构建"
                }
            }
        }

        stage("发布更新"){
            steps{
                script {
                    echo "发布更新"
                }
            }
        }
    }
}