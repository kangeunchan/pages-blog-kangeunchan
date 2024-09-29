---
layout: post
title: Cloud Native Korea Community Day 2024
date : 2024-09-24
parent : Conference
excerpt : 2024년 09월 24일에 열린 Cloud Native Korea Community Day 2024 에 참가한 내용을 정리한 것 입니다.
toc: false
---
### Cloud Native Korea Community Day 2024

2024년 9월 24일에 열린 Cloud Native Korea Community Day 2024는 쿠버네티스를 넘어 다양한 Cloud Native 기술을 다룬 행사였습니다. 아래는 주요 세션의 내용 요약입니다.

---

## 1. Kubernetes 10년, 그 너머의 항해, 살아남은 자의 인사이트
- **Kubernetes의 기본 기능**: 스케줄링, 프로브, 레플리카, 스토리지, Ingress 컨트롤러 등의 핵심 기능이 강조됨.
- **Declarative Kubernetes API**: API 호출을 통한 Kubernetes 제어와 일관된 서비스 제공의 중요성.
- **컨테이너 기술에 대한 거부감**: 안정성에 대한 우려가 있지만, Kubernetes API 버전의 변화에 유연하게 대처해야 함.
- **MSA, CI/CD, 모니터링**: Cloud Native 에코시스템에서 올바른 오픈소스를 선택하는 것이 중요해짐.
- **지속적인 학습과 운**: 새로운 기술에 앞서가기 위해 꾸준한 학습과 커뮤니티 참여의 필요성 강조.

## 2. 엣지로 확장된 Kubernetes - 미래의 클라우드 인프라를 재정의하다
- **Project Gecko**: 엣지 컴퓨팅을 확장하여 분산된 클라우드를 구축하려는 시도. 레이턴시가 적고 지역성을 요구하는 애플리케이션에 강점이 있음.
- **Gecko Region**: 분산 컴퓨팅이 필요한 부분에 적용되며, 특정 AI 데이터를 처리 후 메인 서버로 전송하는 구조.

## 3. F5 CIS와 NGINX의 조합으로 멀티클러스터 네트워킹 단순화 및 자동화
- **Ingress Controller**: 트래픽 제어, API 게이트웨이, 인증, 웹 방화벽 기능을 수행하며 보안 측면에서 중요한 역할을 함.
- **멀티클러스터 네트워킹 자동화**: NGINX Ingress Controller와 F5를 연동하여 클러스터 간 네트워크를 자동화함. DevOps와 NetOps의 완전 자동화 가능성도 제시됨.

## 4. Cloud Native AI
- Kubernetes RBAC을 이용한 사용자 접근 제어 문제점과 이를 해결하기 위한 프록시 서버 기반 접근 제어 방식을 설명.
- **RBAC 개선**: 역할 명세와 RoleBinding의 복잡성을 해결하기 위한 동적 Role 관리와 프록시 서버를 통한 인증 및 로그 관리 방안이 제시됨.

## 5. 쿠버네티스 스케줄러는 노드를 어떻게 선택하는가?
- **스케줄링 프로세스**: 필터 플러그인으로 노드를 선택하고, 점수를 계산하여 가장 높은 점수를 가진 노드를 선택하는 방식 설명.
- **파드 스케줄링 제어**: 파드가 특정 조건에 맞는 노드에 배포되도록 제한하는 방법과 리소스 부족으로 인한 실행 불가 문제 해결 방안 제시.
- **리소스 단편화 문제**: 리소스 단편화로 인해 필요한 리소스를 할당하지 못하는 문제를 해결하기 위해 리소스 사용량이 높은 노드를 우선 선택하는 방식 등 다양한 스케줄러 설정을 소개.

## 6. Cloud Native 서비스의 Multi-AZ/Multi-Region 환경을 위한 HA
- **고가용성(HA)**을 위한 Cloud Native 서비스의 Multi-AZ/Multi-Region 설정을 통한 안정적인 배포 전략에 대한 논의가 있었음.

---

Cloud Native 기술의 다양한 분야에서 최신 트렌드와 실무 경험을 공유하며, 향후 기술 발전 방향에 대해 논의된 의미 있는 행사였습니다.