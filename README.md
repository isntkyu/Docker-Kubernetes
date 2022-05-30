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
