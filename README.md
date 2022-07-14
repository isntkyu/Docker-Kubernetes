# Docker-Kubernetes

docker run -it node
docker run -p localpost:dockerpost imageID (optional)
docker ps -a

---

이미지: 앱을 시작하는데 사용할 수 있는 코드와 도구로 찬 패키지

컨테이너: 이미지를 기반으로 하는 격리된 소프트웨어 유닛. 이미지의 실행중인 인스턴스

이미지 기반으로 컨테이너 실행

이미지는 읽기전용

이미지 레이어 (캐싱)

이미지는 읽기 / 쓰기 액세스 권한이 있는 인스턴스를 실행하는 컨테이너의 블루프린트.(이미지가 인스턴스를 실행하지않음)

여러 컨테이너가 동일 이미지 기반으로 할 수 있지만 서로 완전히 격리됨.

---

docker start 디폴트 detached mode (-a 명령어 가능)
docker run 디폴트 attached mode (-d 명령어 가능)

실행중인 컨테이너에는 docker attach CONTAINERID 가능

- 인터랙티브 모드

-it, -i, 재시작시 -a

---

- 컨테이너 삭제

docker rm (stop 이후)

docker rmi(docker images)

docker image prune (사용하지않는 이미지 전부제거)

docker run --rm (중지시 자동삭제)

---

docker image inspect ID

---

docker cp

---

docker run -o port:port -d --rm --name NAME ID

- 이미지 name:tag(optional)
  docker build -t NAME:tag .

---

- docker hub 에 이미지 푸시, 풀하기
  - docker push / pull
  - docker login / logout

---

- Data

  - Application
    - 코드와 환경.
    - 읽기전용인 이미지에 저장됨
  - Temparary App Data
    - read/write 컨테이너에 저장됨
    - 휘발성 데이터
  - Permanent App Data
    - read/write, 컨테이너와 볼륨에 저장됨.
    - 데이터가 손실되면 안된다.(중지나 재시작시)

- 볼륨
  - 문제)컨테이너가 삭제되면 데이터 소실됨.
  - 컨테이너나 이미지에 있는게 아닌 호스트 머신과 연동
  - 컨테이너가 삭제되어도 사라지지않는 데이터

---

### 바인드 마운트

- 볼륨과 비슷하지만 로컬 호스트머신의 경로을 알고있음
- 영구적이고 편집가능한 데이터에 적합.
- 컨테이너가 스냅샷이 아닌 항상 최신 코드에 액세스하도록 해줌.
- 이미지에 영향 주지않고 컨테이너 실행시 입력 가능 (docker run)

`https://headsigned.com/posts/mounting-docker-volumes-with-docker-toolbox-for-windows/`
