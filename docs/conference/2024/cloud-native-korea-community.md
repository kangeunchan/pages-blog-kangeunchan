---
layout: post
title: Cloud Native Korea Community Day 2024
date : 2024-09-24
parent : Conference
excerpt : 2024년 09월 24일에 열린 Cloud Native Korea Community Day 2024 에 참가한 내용을 정리한 것 입니다.
toc: false
---

# Cloud Native Korea Community Day 2024
kubernetes 를 넘어 Cloud Native 기술을 다루는 행사

## Kubernetes 10년, 그 너머의 향해, 살아남은 자의 인사이트

kubernetes basic function  
scheduling   
probe  
replicas  
storage  
ingress controller  

Declarative Kubernetes API   
Transparent Kubernetes control plane 서비스들이 API를 호출하는 모든 것들이 동일함
Fetching Kubernetes API Data
Workload portabiliy

컨테이너 기술에 대한 거부감
vm 보다 container 가 안정적인가?
버전 업그레이드를 하는데에는 상관없음, 하지만 Kubernetes 의 API 버전이 바뀔 수 있다는 것을 참고
MSA, CI/CD, Monitoring
Ecosysyem 어떤 OpenSourse 를 선택하는 지가 중요한 상황이 됬음

kubernetesㄴ

중요한 . 저

기본 기술이 중요함 -> 앞서 나가는 힘

기본 기술이 없으면 나오는 기술을 이용할 수 없다.

지속적인 학습 -> 전문가

운이 필요함 -> 컨퍼런스 참석 -> 새로운 기술

커뮤니티 -> 핵심

## 엣지로 확장된 kubernetes 미래의 클라우드 인프라를 재정의하다

1. 새로운 클라우드 아키택쳐의 필요성

2. Project Gecko Generalized Edge Compute
클라우드 컴퓨팅 역량을 엣지로 확ㅈ장하여 세계에서 제일 분산된 클라우드를 만들겠다

Core 부분에는 어플리케이션이 올라가고 분산 컴퓨팅이 필요한 부분을 gecko region 에다가 함. Edge 기능에 보안이나 CDN 같은 기능이 올라감

레이턴시가 적은 어플리케이션에 뛰어나고 지역성이있는 어플리케이션에도 성능이 좋음 AI도 노드를 ㄷ분산해서 특정 AI 데이터를 분석하고 Main Server 에다가 올리는 방식으로 할 수 있음.

Gecko Region 은 Fullstack Application 을 배포하는 것이 아니라 분산 컴퓨팅이 필요한 부분에 사용하는 것임.

글로벌 분산 사용자가 있는 곳에서 앱을 실행

## F5 CIS 와 NGINX의 조합으로 멀티클러스터 네트워킹 단순화 및 자동화

k8s 서비스 네트워킹


Ingress 
단순히 요청에 대한 ROUTE 만하는 게아니라 더 많은 일을 할 수 있음

공항에서 Gate 가 1개의 서비스

Nginx Ingress Controller가
L4/L7 트래픽 라우팅
트래픽 제어 
API 게이트웨이
SSO, JWT 인증
웹 방화벽

Ingress Controller 가 가장 보안을 적용하기 적정한 장소임

Pod 에서 들어오는 트래픽 하고 나가는 프래틱 모두 Ingress Controller 가 할 . 수있음

Hacker 트래픽도 다 검사를 할 수 있음


다른 유형의 Ingress 도 이따.

F5 는 클러스터 외부에 있는 내부의 CIS를 배포해서 ingress Resoures CNI 연동이 필요함 별도의 터널링이나 STATIC Routing 이 필요하지 않음, 


k8s 서비스 네트워킹 자동화하기

Nginx Ingress Controller 하고 dhlqndp dlTsms ADC.GSL(F5)로 해서 연동할 수 있음 심지어 자동임!! 

지리네

NetOps 와 DevOps의 연결을 완전 자동화를 할 수 있음

## Cloud Native AI


## 

kubernetes RBAC

사용자 별로 namespace 나누고 kubeconfig를 제공해서 사용
-> cluster 내 충돌을 사용

RBAC 의 문제점

Role 명세를 작성해야함, Rolebinding 을 해야함
멀티 클러스터면 각 클러스터 별로 또 해줘야함

Audit log 각 클러스터마다 해야함. RBAC Deny Rule 의 부제
사용자에게 Nginx만 제외 하려면 white list 기반의 rules  하나씩 rule 을 다 추가해야함

RBAC 패턴 매칭 기능의 붇제
resource name 을 모두 적어줘야함.

접근 제어를 담당하는 프록시 서버를 만들어서 쿠버네티스 API 압단에 둠

client 툴은 kubernetes 압단에 위치함.

client 와 k8s 사이에 위치함

client 가 보내는 요청을 가로체서 인증 인가하고 audit 로그를 남김 pod session recording, 응답 필터링을 해줌

동작

매 요청마다 proxy 서버에서 정책을 체크하여 접을 허용하고 차단함

proxy 서버에서 정책을 체크하려면 인증정보를 받아야함 보통은 kubeconfig를 사용해서만들어짐

kubeconfig 를 어떻게 관리해야할까에 대한 고민을 하게됨 agent 를 사용자 local에다 두고 agent 가 접근제어 서버에 사용자가 인증하게 함

multi cluster & multi role
agent 를 이용해서 동적으로 role에 대한 정보가 동적으로 변경되게 함

proxy 로 어떻게 정보를 전달할까

agent 에게 토큰을 생성하게 하고 agent 는 exec plugin 응답 포멧에 맞추어 토큰을 생성함

구현 하기 위해서 무엇에 어떤 요청을 보내는지 확인 해야했음

rest api 를 사용한 부분이 있었꼬 

spdy 프로토콜을 사용한 부분도 있었음

event stream 부분도 있었음

kubernetes API verb 로 바꿔서 해석하고 있엇음

RBAC 명세는 어떻게 개선 했는가?

자체적인 policy 명세를 개발함

resource = cluster

subjects = role

actions = action

conditions = cluster property and user property

multi cluster
클러스터 리스트를 동기화 해서 접근 제어 서버에서 볼 수 있음

관리자가 각 clauset 마다 tag 를 지정할 수 있음

## 쿠버네티스 스케줄러는 노드를 어떻게 선택하는가?

세션에서 다룰 내용
스케줄러가 파드 배포를 위해 노드를 선택하는 과정
스케줄러가 선택하는 노에 영향을 주는 파드 속성
스케줄러 성는에 영향을 주는 설정
리소스 단편화
리소스 사용량 확대 전략

필터 플러그인에 파드와 노드를 입력해 조건을 만족하는지 검사

모든 노드를 검색하지 않도록 검색할 노드의 최대 크기 제한

필터링을 통과한 모든 노드를 대상으로 점수 계산 및 순위 정렬
플러그인에 노드 정보와 파드 정보를 입력해 점수 계산

가장 높은 순위를 가진 노드를 파드에 할당
동일할 경우 랜덤 선택

파드 스케줄링 제어

파드를 특정한 조건을 가진 노드에서만 실행되도록 제한
파들를 여러조건에 맞는 노드중 하나에서 실행되도록 제한
ㅏ드를 특별한 장치를 가진 노드에 배포
서로다른 두 파드를 동일한 노드 혹은 동일한 가용영역에 배포
명시적인 파드 스케줄링 대기

노드 레이블
노드의 특징, 리소스, 성능 등 다양한 정보를 레이블로 표현
쿠버네티스 노드의 기본 레이블과 권장 레이블

파드 스케줄링 대기
파드 생성 후 스케줄링이 일어나는 시점을 제어할때 사용가능
스케줄링게이트 필드에 필요한 리소스등을 추가해 표시
이러면 스케줄링이 되지 않음
명시적인 제어가 가능해짐

STATUS 에 SchedulingGat 라고 뜸

스체줄링 게이트 상태일때는 강화만 가능함

파드를 생성할때 spec.nodename 필드에 원하는 노드 지정

파드 spec.nodeselector 필드에 노드 레이블 지정
지정한 노드 레이블이 모두 있는 노드만 선택
간단하게 노드 선택에 제약을 줄 수 있는 노드 설정

해당 노드에 리소스가 부록하거나 레이블이 일치하지 않으면 padding이 되버림

선호도 기반 포

노드셀렉터 방식 보다 다양한 표현 방식 지원

정의한 값이 정수로 변환되지 않으면 스케줄링이 실패함 NodeAffinity 에서만 사용가능 

required 는 노드 셀렉터 처럼 다 만족해야함

preferred 는 가중치를 설정해서 배포를 생성함

선호도 기반 배포 pod 

실행중인 파드 레이블을 기반으로 배포할 노드 제한가능

파드 역할 목적에 따라 분산시키거나 같이 실행되도록 제어

대규모 클러스터에서는 스케줄링 속도가 느려질 수 있음 멀티 클러스터에서 불리함

다른 node 와 동일한 존에 웹 파드를 설치할 수 있음

리소스가 부족하면 배포 불가

preferred 는 옆에 서치됨


mactchlabelkeys
pod affinity 조건에 일치할 파드 레이블 키 추가 지정

pod template 는 선호도 개산을 동일한 리비전에있는 파드끼리 하겠다는 거임.

topology spread constraints 


ㅅ먀ㅜㅅㄴ dhk 새ㅣㄷㄱㅁ샤ㅐㅜㄴ 

노드에서 파드를 제외하는 형태로 제어하고 싶을때 사용

리소스 단편화

클러스터 전체적인 리소스 여유 공간은 충분한 상태인데
하지만 파드에서 요청한 일부 리소스 부족으로 인해 실행 불가함
릿소스 단편화로 인해 필요한 리소스를 한 노드에서 모두 할 당할 수 없는 상황

스케줄러는 기본적으로 리소스가 좀 더 남아있는 노드 선택

항상 1 GPY 리소스만 요청한다면 상관없음

Resource Bin padking 리소스 사용량이 높은 노드를 먼저 선택해 사용하는 방식

noderresourcefit 스코어ㄹ링을설정을 변경해 적용
leastallocatied 노드 사용량이 낮은 노드를 먼저 선택
most allocated 노드 사용량이 높은 노드를 먼저 선택

새로운 스케줄ㄹ ㅓ추가 configmap ㅣㄹ소스 생성

스켖둘러 설정이 저장된 configmap을 볼륨으로 연결

스케줄러 실행 옵션에 앞에서 생성한 스케줄러 설정 파일 지정

파드를 생성할때 새로 생성한 스케줄러 이름을 지정해 사용

k8s-1를 채우고 k8s-2 를 채우는 형태로 배포가 됨

## Cloud Native 서비스의 Multi-AZ/Multi-Region 환경을 위한 HA

