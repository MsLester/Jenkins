pipeline {
    agent any

    stages {
        stage('拉取代码') {
            steps {
                echo 'Jenkins 已从 GitHub 拉取代码'
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('部署网页') {
            steps {
                echo '开始部署网页'
                sh 'mkdir -p /var/jenkins_home/web/python-web-ci'
                sh 'cp -f index.html /var/jenkins_home/web/python-web-ci/index.html'
            }
        }

        stage('验证部署') {
            steps {
                echo '验证部署结果'
                sh 'ls -l /var/jenkins_home/web/python-web-ci'
                sh 'grep "第1次发布" /var/jenkins_home/web/python-web-ci/index.html'
            }
        }
    }
}
