# 클러스터 관리 도구

> Cluster Manager</br>복수의 Docker 컨테이너 관리

- 특정 기능을 실현하는데 특화된 Docker를 협조 동작시키기 위한 것
- 여러 Docker Daemon으로 이루어진 시스템 전체를 의도한 상태로 유지하기 위한 것
- Docker만으로는 여러 host(node)의 docker Daemon을 통합 관리/이용이 불가하다

- K8s는 여러 노드에 있는 Docker Container를 관리한다( 노드 관리 X )

## Kubernetes의 기본 개념
> 1. 노드
> 2. 팟
> 3. 서비스
> 4. 리플리케이션 컨트롤러
> 5. 라벨

### 1. 노드(node)
| 이름 | 설명 |
|---|---|
|노드(NODE)| Docker데몬이 동작하는 호스트|
|마스터(Master)|클러스터 제어용 프로그램이 동작하는 호스트</br>K8s 제어API를 수신|
|미니언(워커노드)|컨테이너 동작

### 2. 팟(pod)
- Docker 컨테이너 집합체(set)
- docker-compose나 Kubernetes를 사용해 set로 배치
- 1컨테이너-1프로세스를 유지하며 K8s 관리하에 세트로 배치하는 것이 팟
- 팟을 리플리케이션 컨트롤러 정의 안에 기술 가능

### 3. 서비스
- 통신의 엔드포인트로서 연결된 팟으로 통신을 분산
- 서비스와 팟은 라벨로 결합

### 4. 리플리케이션 컨트롤러
- 팟 배포를 관리
- 다중도를 정의, 감시, 조정

### 5. 라벨
- 오브젝트에 부여할 수 있는 속성으로 복수개 설정 가능
- 라벨을 기반으로 오브젝트를 지정

## k8s의 구성 요소
- 기본
    - Docker
    - etcd
    - kubelet
    - kube-proxy
    - kube-apiserver
    - kube-controller-manager
    - kube-scheduler
- add-on
    - DNS(SkyDNS + kube2sky)
    - UI(kube-ui)
    - 모니터링(Heapster, grafana, InfluxDB)
 
 ## K8s의 네트워크
 