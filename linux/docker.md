# 🐳 Docker

도커란, 컨테이너의 형태로 프로그램을 올려 이식성이 높은 방법이다.

---

## ⌨ Docker 명령어

### Docker 컨테이너 목록 조회

```shell
    $ docker container ls [OPTIONS]
```

- 현재 기동중인 컨테이너 목록 확인
- OPTIONS
  - -a : 중지된 컨테이너까지 포함한 모든 컨테이너 목록 조회

### Docker 로그확인하기

```shell
    $ docker container logs [OPTIONS] [CONTAINER_NAME]
```

- OPTIONS
  - -t
  - --tail : 실시간으로 로그확인 몇줄부터 볼껀지 뒤에 숫자도 표기 ex) --tail 200
