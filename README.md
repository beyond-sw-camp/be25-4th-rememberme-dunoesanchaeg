# 두뇌산책

<img width="1000" alt="두뇌산책_대표_이미지" src="./images/두뇌산책대표이미지.jpg" />


## 👥 팀원 소개

<table style="width:100%; text-align:center;">
  <thead>
    <tr>
      <th>양준석</th>
      <th>박재하</th>
      <th>모희주</th>
      <th>윤준상</th>
      <th>이슬이</th>
      <th>조하은</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <img src="./images/이미지1.jpg" style="width:120px; height:140px; object-fit:contain;"><br>
        🔗 <a href="https://github.com/YJunSuk">YSunSuk</a>
      </td>
      <td>
        <img src="./images/이미지2.png" style="width:120px; height:140px; object-fit:contain;"><br>
        🔗 <a href="https://github.com/horolo1234">horolo1234</a>
      </td>
      <td>
        <img src="./images/이미지3.png" style="width:120px; height:140px; object-fit:contain;"><br>
        🔗 <a href="https://github.com/heejudy">heejudy</a>
      </td>
      <td>
        <img src="./images/이미지4.png" style="width:120px; height:140px; object-fit:contain;"><br>
        🔗 <a href="https://github.com/wnstkd704">wnstkd704</a>
      </td>
      <td>
        <img src="./images/이미지5.png" style="width:120px; height:140px; object-fit:contain;"><br>
        🔗 <a href="https://github.com/0lthree">0lthree</a>
      </td>
      <td>
        <img src="./images/이미지6.jpg" style="width:120px; height:140px; object-fit:contain;"><br>
        🔗 <a href="https://github.com/haeuniiii">haeuniiii</a>
      </td>
    </tr>
  </tbody>
</table>

<br>


## 📍 목차

1. [프로젝트 개요](#1-프로젝트-개요)
2. [배경 및 필요성](#2-배경-및-필요성)
3. [기술 스택](#3-기술-스택)  
4. [시스템 아키텍처](#4-시스템-아키텍처)
5. [요구사항 정의서](#5-요구사항-정의서)
6. [테이블 정의서](#6-테이블-정의서)
7. [API 명세서](#7-API-명세서)
8. [백엔드 테스트 보고서](#8-백엔드-테스트-보고서)
9. [프론트엔드 테스트 보고서](#9-프론트엔드-테스트-보고서)
10. [CI/CD](#10-CI/CD)
11. [회고](#11-회고)

<br>


## <a id="1-프로젝트-개요"></a> 1. 프로젝트 개요  

본 프로젝트는 치매 예방을 목적으로 하는 웹사이트를 개발하는 것을 목표로 한다.

<img width="645" height="280" alt="인구고령화 자료" src="https://github.com/user-attachments/assets/b9c52e23-bf9f-46b0-a856-14e1c06ceeb1" />
<br>

최근 인구 고령화가 빠르게 진행되면서 치매 환자 수 또한 지속적으로 증가하고 있으며, 이에 따라 개인과 사회가 부담해야 하는 경제적·사회적 비용 또한 점점 커지고 있다. 이러한 문제를 예방적인 관점에서 접근하기 위해, 사용자가 일상 속에서 간단한 두뇌 활동을 꾸준히 수행할 수 있도록 돕는 웹 기반 서비스를 기획하였다.

본 웹사이트는 사용자에게 매일 미션 3가지를 제공하여 지속적인 두뇌 활동을 유도한다. 제공되는 미션은 미니 게임, 개방형 질문, 하루 기록으로 구성되어 있으며, 각각의 활동을 통해 기억력과 사고력 등을 자극하고 자신의 일상생활을 돌아볼 수 있도록 설계하였다.

먼저 미니 게임은 문제의 지시사항을 읽고 그에 맞는 정답을 선택하는 방식으로 진행되며, 사용자가 간단한 문제 해결 과정을 통해 두뇌를 활용하도록 돕는다. 개방형 질문은 사용자가 단순한 단답형 답변이 아닌 자신의 과거 경험이나 기억을 떠올리며 서술하도록 유도하여 회상 능력과 사고 활동을 촉진한다. 마지막으로 하루 기록은 사용자가 자신의 하루를 돌아보며 오늘의 기분, 식사, 수면 등 생활 패턴을 기록하도록 하여 일상에 대한 인식과 자기 성찰의 시간을 갖는다.

이와 같은 기능을 통해 사용자가 일상 속에서 자연스럽게 두뇌 활동을 지속할 수 있도록 하여 치매 예방에 긍정적인 영향을 줄 수 있는 웹 서비스를 제공하고자 한다.

<br>


## <a id="2-배경-및-필요성"></a> 2. 배경 및 필요성

중앙치매센터[[1]](https://www.nid.or.kr/info/dataroom_view.aspx?bid=317)에 따르면, 전국 65세 이상 추정 치매 환자 수는 2019년 이후 매년 증가하는 추세를 보이며 2023년에는 약 87만 명으로 전년 대비 약 5.1% 증가한 것으로 나타났다.

<img width="645" height="486" alt="치매환자수 자료" src="https://github.com/user-attachments/assets/354e3c0c-7009-4762-8fd3-0fd007cca103" />
<br>

치매 환자의 증가와 함께 경제적 부담 또한 큰 문제로 대두되고 있다. 치매 환자 1인당 연간 관리 비용은 연간 가구 소득의 약 43.8%에 해당하는 수준으로 나타나 개인과 가족에게 상당한 부담이 되고 있다. 향후 고령 인구의 증가와 함께 치매 환자 수 역시 지속적으로 증가할 것으로 예상되기 때문에, 치매를 치료하는 것뿐만 아니라 사전에 예방하는 것이 매우 중요하다.

<img width="645" height="384" alt="치매치료비 자료" src="https://github.com/user-attachments/assets/bfd7fa62-85ca-457d-ade4-6784766a12fa" />
<br>

치매 예방을 위해서는 낱말 맞추기, 글쓰기, 문화 및 취미 활동과 같이 뇌세포를 지속적으로 자극할 수 있는 두뇌 활동을 꾸준히 수행하는 것이 중요한 것으로 알려져 있다. 특히 이러한 활동을 즐겁고 지속적으로 수행하는 것이 장기적인 예방 효과에 긍정적인 영향을 줄 수 있다.

이에 본 프로젝트에서는 사용자가 일상생활 속에서 부담 없이 참여할 수 있는 웹 기반 치매 예방 서비스를 기획하였다. 사용자가 매일 간단한 미션을 수행하면서 지속적인 두뇌 활동을 유도하고 치매 예방에 도움을 줄 수 있는 환경을 제공하고자 한다.

<br>


## <a id="3-기술-스택"></a> 3. 기술 스택

### BACKEND
![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white)
<img src="https://img.shields.io/badge/SpringBoot-10B146?style=for-the-badge&logo=SpringBoot&logoColor=white">

### FRONTEND
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![Vue.js](https://img.shields.io/badge/vuejs-%2335495e.svg?style=for-the-badge&logo=vuedotjs&logoColor=%234FC08D)

### DATABASE
![mariadb](https://github.com/user-attachments/assets/19a0ad09-804d-4303-80bd-32cafdae0e6f)

### DEPLOYMENT
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)

![Route53](https://img.shields.io/badge/Route%2053-7046E5?style=for-the-badge)
![CloudFront](https://img.shields.io/badge/CloudFront-7046E5?style=for-the-badge)
![S3](https://img.shields.io/badge/S3-FF9900?style=for-the-badge)

![ALB](https://img.shields.io/badge/Application%20Load%20Balancer-7046E5?style=for-the-badge)
![EC2](https://img.shields.io/badge/EC2-FF9900?style=for-the-badge)
![RDS](https://img.shields.io/badge/RDS-0073BB?style=for-the-badge)

![CloudWatch](https://img.shields.io/badge/AWS%20CloudWatch-C925D1?style=for-the-badge)

### FRAMEWORKS, PLATFORMS, LIBRAIRES
![Chart.js](https://img.shields.io/badge/chart.js-F5788D.svg?style=for-the-badge&logo=chart.js&logoColor=white)
![axios](https://img.shields.io/badge/axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white)
![pinia](https://img.shields.io/badge/pinia-7E0C1B?style=for-the-badge&logo=pinia&logoColor=white)
![NPM](https://img.shields.io/badge/NPM-%23CB3837.svg?style=for-the-badge&logo=npm&logoColor=white)

![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
![Vite](https://img.shields.io/badge/vite-%23646CFF.svg?style=for-the-badge&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)

![springsecurity](https://img.shields.io/badge/springsecurity-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)
![Maven](https://img.shields.io/badge/apachemaven-C71A36.svg?style=for-the-badge&logo=apachemaven&logoColor=white)

### DOCUMENTATION
![Swagger](https://img.shields.io/badge/-Swagger-%23Clojure?style=for-the-badge&logo=swagger&logoColor=white)

### DEVOPS
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"> <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white"> <img src="https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white"> <img src="https://img.shields.io/badge/Argo%20CD-FE6A16?style=for-the-badge&logo=argo&logoColor=white"> <img src="https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white">

<br>


## <a id="4-시스템-아키텍처"></a> 4. 시스템 아키텍처

<img src="./images/CICD시스템아키텍처.png" />

<br>


## <a id="5-요구사항-정의서"></a> 5. 요구사항 정의서

<details>
<summary><b>🗒️ 요구사항 정의서 링크</b></summary>

- [요구사항 정의서](https://docs.google.com/spreadsheets/d/1cGxKolGeDWGtzUYxWShYSNCS0KK_gclYAco5hxDQDqI/edit?gid=1415182395#gid=1415182395)

</details>
<br>


## <a id="6-테이블-정의서"></a> 6. 테이블 정의서

<details>
<summary><b>🗄️ 테이블 정의서 링크</b></summary>

- [테이블 정의서](https://docs.google.com/spreadsheets/d/1W4umq2TJ3RlpNsyxd6Db3YlDfhOW4DBUH2VfQkSFBGc/edit?gid=0#gid=0)

</details>
<br>


## <a id="7-API-명세서"></a> 7. API 명세서

<details>
<summary><b>📋 API 명세서 링크</b></summary>

- [API 명세서](https://www.notion.so/API-308dd863c93280e2808fdca71cc4adde)

</details>
<br>


## <a id="8-백엔드-테스트-보고서"></a> 8. 백엔드 테스트 보고서

<details>
<summary><b>🧾 백엔드 테스트 보고서 링크</b></summary>

- [백엔드 테스트 보고서](https://docs.google.com/spreadsheets/d/1cGxKolGeDWGtzUYxWShYSNCS0KK_gclYAco5hxDQDqI/edit?gid=211938515#gid=211938515)

</details>
<br>


## <a id="9-프론트엔드-테스트-보고서"></a> 9. 프론트엔드 테스트 보고서

<details>
<summary><b>🧾 프론트엔드 테스트 보고서 링크</b></summary>

- [프론트엔드 테스트 보고서](https://docs.google.com/spreadsheets/d/1cGxKolGeDWGtzUYxWShYSNCS0KK_gclYAco5hxDQDqI/edit?gid=687771753#gid=687771753)

</details>
<br>


## <a id="10-CI/CD"></a> 10. CI/CD

### 📌 시나리오

#### 1. 코드 업데이트 (Git Push)
개발자가 수정한 코드를 GitHub develop 브랜치에 commit & push 하여 전체 자동화 프로세스를 트리거합니다.
<br>

#### 2. 이벤트 전달 (Webhook)
GitHub는 Webhook을 통해 실시간으로 변경 이벤트를 Jenkins 서버에 전달합니다.
<br>

#### 3. CI 단계: 빌드 및 이미지 업로드 (Jenkins)
변경 감지: Jenkins 파이프라인이 이전 커밋과 비교하여 백엔드/프론트엔드 변경 사항을 식별합니다.<br/>
Docker 빌드: 변경된 파트의 도커 이미지를 생성하고 Docker Hub에 업로드합니다.<br/>
설정 업데이트: deployment.yml 파일의 이미지 태그를 최신화하여 Manifest 저장소에 push 합니다.
<br>

#### 4. CD 단계: 자동 동기화 및 배포 (ArgoCD)
Git 감지: ArgoCD가 Git 저장소의 상태 변화를 자동으로 감지합니다.<br/>
무중단 배포: 백엔드와 프론트엔드 각각의 변경 사항을 쿠버네티스 클러스터에 무중단으로 반영합니다.
<br><br>


### ⚙️ 파이프라인 스크립트

<details>
<summary><b>Jenkins Pipeline</b></summary>

```groovy
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
```

</details>

<details>
<summary><b>k8s manifest Pipeline</b></summary>

```groovy
pipeline {
    agent any

    parameters {
        string(name: 'IMAGE_TAG', defaultValue: '', description: 'Docker Image Version')
        string(name: 'DID_BUILD_FRONTEND', defaultValue: '', description: 'Did Build Frontend')
        string(name: 'DID_BUILD_BACKEND', defaultValue: '', description: 'Did Build Backend')
    }

    stages {
        stage('Checkout Main Branches') {
            steps {
                sh 'git checkout main'
                echo "IMAGE_TAG: ${params.IMAGE_TAG}"
                echo "DID_BUILD_FRONTEND: ${params.DID_BUILD_FRONTEND}"
                echo "DID_BUILD_BACKEND: ${params.DID_BUILD_BACKEND}"
            }
        }

        stage('update frontend deployment.yaml') {
            when {
                expression {
                    return params.DID_BUILD_FRONTEND == "true"
                }
            }
            steps {
                dir('rememberme-frontend') {
                    echo "Received Docker Image Version : ${params.IMAGE_TAG}"
                    sh "sed -i 's|yjs0530/rememberme-frontend:.*|yjs0530/rememberme-frontend:${params.IMAGE_TAG}|g' deployment.yaml"
                    sh 'cat deployment.yaml'
                }
            }
        }

        stage('update backend deployment.yaml') {
            when {
                expression {
                    return params.DID_BUILD_BACKEND == "true"
                }
            }
            steps {
                dir('rememberme-backend') {
                    echo "Received Docker Image Version : ${params.IMAGE_TAG}"
                    sh "sed -i 's|yjs0530/rememberme-backend:.*|yjs0530/rememberme-backend:${params.IMAGE_TAG}|g' deployment.yaml"
                    sh 'cat deployment.yaml'
                }
            }
        }

        stage('Commit & Push') {
            when {
                expression { 
                    return params.DID_BUILD_FRONTEND == "true" || params.DID_BUILD_BACKEND == "true"
                }
            }
            steps {
                sh 'git config --list'
                sh 'git config user.name "jenkins"'
                sh 'git config user.email "jenkins@beyond.com"'
                sh "git add ."
                sh "git commit -m 'Update RememberMe Image Version ${params.IMAGE_TAG}'"
                sh 'git status'

                sshagent(['github-k8s-manifests']) {
                    sh 'git push origin main'
                }
            }
        }
    }
}
```

</details>

<br>


### ✅ 실행 결과

<details>
<summary><b>실행 결과 링크</b></summary>
  
<br>
<img src="./images/실행결과썸네일.png" width="1000" alt="실행_결과_썸네일" /></br>

- [실행 결과 영상](https://youtu.be/AMrLpmCyrm4)

</details>
<br>


## <a id="11-회고"></a> 11. 회고

|   이름   |     회고 내용     |
|-----------|-----------------|
|      양준석      |     이번 DevOps 프로젝트를 통해 현업에서 어떻게 함께 일을 진행하는지 어느 정도 알 수 있게 되었다. 이미 만들어져 있는 환경에서 Github에 커밋과 푸시만 하면, CI/CD를 통해 테스트와 통합이 자동으로 이루어지고, 마지막 단계에서 배포까지 진행되는 느낌이었다. CI/CD는 개발 단계와 달리 여러 오픈소스 플랫폼을 활용하고 어플리케이션을 통합해야 하기 때문에, 어떤 아키텍처를 구성하느냐가 매우 중요한 부분이었다. 같은 작업을 해도 환경이 다르면 오류가 발생하는 등 어려움이 한두 가지가 아니었다. 하지만 자동화된 환경 구성을 한 번 해놓으면, 실제 작업할 때 드는 시간이 크게 줄어드는 경험을 해서 정말 좋았다.     |
|      박재하      |     인프라 설계를AWS 인프라를 Kubernetes 환경으로 전환하고 CI/CD를 적용하면서 많은 점들을 배울 수 있었다. Pod를 통한 자원 격리와 자가 치유기능을 활용해 서비스 운영의 안정성을 확보를 경험했다. 특히 젠킨스를 통한 빌드와 테스트의 자동화, 아르고CD를 이용한 지속적인 배포를 통해 소프트웨어 생명주기에 대해 정확하게 배울 수 있었다. 또한 동일 클러스터 내에서 DB와 Spring Boot 애플리케이션, Vue.js 어플리케이션을 한 번에 올리는 경험을 통해 인프라 복잡도를 효율적으로 제어하는 법을 배웠다. 마지막으로 HPA를 통해 실제 워크로드에 따른 서버 임계치를 설정하고 오토스케일링하는 과정을 통해 무중단 서비스와 고가용성 확보가 안정적인 서비스 운영의 최우선 가치임을 깨달았다.     |
|      모희주      |     데브옵스 프로젝트를 통해 전체적인 CI/CD 구조와 흐름을 이해할 수 있었다. 진행 과정에서 예상보다 많은 오류를 겪었고, 이를 해결하는 데 시간이 걸렸지만 그만큼 실무에 가까운 경험을 할 수 있었다. 특히 카카오 로그인 연동 과정에서 단순한 설정 문제가 아니라 Kubernetes Pod 상태와 이미지 미반영으로 인해 잘못된 포트로 라우팅되는 문제를 겪었고, 이를 해결하면서 인프라와 애플리케이션이 어떻게 연결되는지 이해할 수 있었다. 또한 secret.yaml과 같은 민감 정보 파일이 Git에 올라가지 않도록 .gitignore로 관리해야 한다는 점도 중요하게 배웠다. 수업 시간에서는 경험해볼 수 없는 오류들을 마주치고 그걸 해결하는 과정에서 많이 배운 것 같다.     |
|      윤준상      |     이번 CI/CD 구축 과정에서는 Jenkins, Docker, Kubernetes, ArgoCD를 활용하여 자동 배포 환경을 구성하였다. 단순히 배포 자동화를 만드는 것보다, 실제 서비스가 어떤 흐름으로 운영되는지 이해하는 데 큰 의미가 있었다. 아직은 Kubernetes와 ArgoCD 설정을 직접 설계하는 과정에서 익숙하지 않은 부분이 많았지만, 로그를 통해 문제 원인을 추적하고 하나씩 수정하면서 장애를 해결하는 경험을 할 수 있었다. 특히 kubectl logs, Startup Probe, 환경 변수 주입 방식 등을 직접 다뤄본 경험은 이후 운영 환경을 이해하는 데 큰 도움이 될 것이라고 생각한다. 앞으로는 현재 구성한 CI/CD 파이프라인을 기반으로 운영 환경 분리(dev/staging/prod), Helm Chart 적용, 모니터링(Prometheus/Grafana), 무중단 배포(Rolling Update, Blue-Green) 등까지 확장해보며 더 안정적인 배포 환경을 구성해보고 싶다.     |
|      이슬이      |     이전 프로젝트의 마지막 단계에서 코드를 반복 수정하며, 이미 CI/CD의 중요성을 어느 정도 체감하고 있었다. 실제 작은 수정 하나를 반영하기 위해 반복적으로 빌드와 배포를 진행하다 보니, 이 과정을 자동화할 수 있다면 훨씬 효율적이겠다는 생각을 했다. 하지만 막상 직접 구축해보니 환경 변수 설정부터 서버와의 연결, 배포 이후의 안정성까지 확인해야 할 부분들이 많았다. 특히 자동화된 흐름이 어떤 방식으로 동작하는지 이해하는 데 시간이 꽤 걸렸다. 그럼에도 이 과정을 겪으면서 단순히 기능을 구현하는 것에서 끝나는 것이 아니라, 실제 서비스를 안정적으로 운영하기 위해서는 배포와 자동화 역시 개발의 중요한 일부라는 점을 깊이 알 수 있었다.     |
|      조하은      |     부트캠프에서 가장 배우고 싶었던 분야가 DevOps였던 만큼, 실제 서비스 운영 환경을 직접 경험할 수 있었다는 점에서 더욱 의미 있는 프로젝트였다. 프로젝트를 진행하면서 로컬에서는 정상적으로 동작하던 기능이 배포 환경에서 예상치 못한 문제를 일으킨다는 것을 처음 체감했다. 로그인 기능에서 CORS로 인해 인증 쿠키가 차단되는 문제가 발생했는데, 원인을 추적하는 과정에서 Spring Security 설정, Credential 허용 옵션, 브라우저 쿠키 정책까지 함께 고려해야 한다는 것을 알게 되었다. 이후 Nginx Reverse Proxy를 적용해 요청 경로를 통합함으로써 문제를 해결할 수 있었다. 이 경험을 통해 하나의 기능이 동작하기 위해서는 코드뿐만 아니라 네트워크, 인증, 서버 설정 등 다양한 요소가 유기적으로 연결되어 있다는 점을 깨달았다. 또한 Jenkins, Kubernetes, ArgoCD를 활용해 CI/CD 및 GitOps 구조를 직접 구성하면서, DevOps란 단순한 배포 역할을 넘어 서비스 전체 흐름을 이해하고 안정적으로 운영하는 과정임을 몸소 익힐 수 있었다.     |
