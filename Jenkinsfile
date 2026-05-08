pipeline {
    agent {
        kubernetes {
            yaml '''
            apiVersion: v1
            kind: Pod
            metadata:
              name: jenkins-agent
            spec:
              containers:
              - name: docker
                image: docker:29.4.1-cli-alpine3.23
                command:
                - cat
                tty: true
                volumeMounts:
                - mountPath: "/var/run/docker.sock"
                  name: docker-socket
              - name: maven
                image: maven:3.9.6-eclipse-temurin-21
                command:
                - cat
                tty: true
              volumes:
              - name: docker-socket
                hostPath:
                  path: "/var/run/docker.sock"
            '''
        }
    }

    triggers {
        githubPush() 
    }

    environment {
        DOCKER_CREDENTIALS_ID = 'dockerhub-access'
        DOCKER_REGISTRY = 'yjs0530'
        BACKEND_IMAGE = "${DOCKER_REGISTRY}/rememberme-backend"
        FRONTEND_IMAGE = "${DOCKER_REGISTRY}/rememberme-frontend"
        GITOPS_REPO = 'github.com/YJunSuk/devops-k8s-manifests.git'
        IMAGE_TAG = "${BUILD_NUMBER}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Detect Changes') {
            steps {
                script {
                    def changedFiles = sh(script: 'git diff --name-only HEAD~1', returnStdout: true).trim().split("\n")

                    echo "Changed files:\n${changedFiles.join('\n')}"
                    env.SHOULD_BUILD_FRONTEND = changedFiles.any { it.startsWith("devops-frontend/") } ? "true" : "false"
                    env.SHOULD_BUILD_BACKEND = changedFiles.any { it.startsWith("devops-backend/") } ? "true" : "false"
                    echo "SHOULD_BUILD_FRONTEND : ${env.SHOULD_BUILD_FRONTEND}"
                    echo "SHOULD_BUILD_BACKEND : ${env.SHOULD_BUILD_BACKEND}"
                }
            }
        }
        stage('Backend Build') {
            when {
                expression { return env.SHOULD_BUILD_BACKEND == "true" }
            }
            steps {
                container('maven') {
                    dir('devops-backend') {
                        sh 'mvn clean package -DskipTests -B'
                    }
                }
            }
        }
        stage('Docker Login') {
            when {
                expression { return env.SHOULD_BUILD_FRONTEND == "true" || env.SHOULD_BUILD_BACKEND == "true" }
            }
            steps {
                container('docker') {
                    sh 'docker logout'

                    withCredentials([usernamePassword(
                        credentialsId: DOCKER_CREDENTIALS_ID,
                        usernameVariable: 'DOCKER_USERNAME',
                        passwordVariable: 'DOCKER_PASSWORD'
                    )]) {
                        sh 'echo $DOCKER_PASSWORD | docker login -u $DOCKER_USERNAME --password-stdin'
                    }
                }
            }
        }
        stage('Docker Build & Push - Backend') {
            when {
                expression { return env.SHOULD_BUILD_BACKEND == "true" }
            }
            steps {
                container('docker') {
                    dir('devops-backend') {
                        sh "docker build --no-cache -t ${BACKEND_IMAGE}:${IMAGE_TAG} ."
                        sh "docker push ${BACKEND_IMAGE}:${IMAGE_TAG}"
                    }
                }
            }
        }
        stage('Docker Build & Push - Frontend') {
            when {
                expression { return env.SHOULD_BUILD_FRONTEND == "true" }
            }
            steps {
                container('docker') {
                    dir('devops-frontend') {
                        sh """
                            docker build --no-cache \
                                --build-arg VITE_KAKAO_CLIENT_ID=a3c925bb3ea42d42e7214bbed14cf347 \
                                --build-arg VITE_KAKAO_REDIRECT_URI=http://localhost:30180/kakao-auth \
                                --build-arg VITE_API_BASE_URL=/api/v1 \
                                -t ${FRONTEND_IMAGE}:${IMAGE_TAG} .
                        """
                        sh "docker push ${FRONTEND_IMAGE}:${IMAGE_TAG}"
                    }
                }
            }
        }
        stage('Trigger k8s-manifests') {
            steps {
                script {
                    build job: 'rememberme-k8s-manifests', 
                        parameters: [
                            string(name: 'IMAGE_TAG', value: "${IMAGE_TAG}"),
                            string(name: 'DID_BUILD_FRONTEND', value: "${env.SHOULD_BUILD_FRONTEND}"),
                            string(name: 'DID_BUILD_BACKEND', value: "${env.SHOULD_BUILD_BACKEND}")
                        ],
                        wait: true
                }
            }
        }
    }
}
