# Linux Command
: 새로 알게되거나 자주 쓰는 명령어 정리

#### 🔨 세션 타임아웃
설정되어있는 세션 타임아웃으로 인한 SSH 사용 막힘 방지
```shell
> TMOUT=0 # 현재 연결에 대해 일시적
```
영구적으로 설정할려면 설정파일에 기재해줘야한다. <sub>(ex, etc/profile)</sub>
- 윈도우 환경에서 putty를 사용할 경우 `PuTTY Configuration > Connection` 에서 설정 가능

#### 🔨 압축 명령어
소스반영시 기존 소스를 백업하기 위해 해당 명령어 사용
```shell
# tar 로 압축하기
tar -cvf [압축파일명.tar] [압축할 대상]

tar -cvf ROOT.tar ~/ROOT/* # ROOT 하위 모든 파일 압축

# tar.gz 로 압축하기
tar -zcvf [압축파일명.tar.gz] [압축할 대상]
```

#### 🔨 방화벽 확인
타 시스템과 연계/호출해야 할 때, 방화벽을 확인해야함!
1. telnet
    ```shell
    # 1. telnet 설치 확인
    > telnet # 입력시 사용할수 없다고 나오면 설정해줘야함.

    # 2. telnet 명령어 사용
    > telnet [ip] [port]
    ```
    telnet 명령어 입력시 해당 ip로 연결할수 있게 telnet 창이 연결되면 방화벽 확인 완료
    > [윈도우에서 telnet 설정](https://cofs.tistory.com/280)

2. netstat    

    **현재 리눅스**에서 열려있는 포트 확인
        
    ```shell
    > netstat -tnlp
    # TCP (t) 중에서, LINSTEN 상태인 것들만 상세정보(p), 10진수 숫자(n)로 표기

    > netstat | grep "LISTEN" # 특정 단어로 검색도 가능
    ```
3. nc
    netcat, 네트워크 연결에서 데이터를 읽고 쓰는 간단한 유틸리티 제공
    ```shell
    # 1. nc 설치 확인
    > nc # -bash: nc: command not found -> 설치안됨
    
    # 2. nc 명령어 사용
    > nc -z [ip] [port] # CentOS 인 경우 -z 생략가능
    # -z 요청시 최소한의 데이터로만 진행
    ```
4. curl
    서버상에서 http 요청에 대해 확인할 때 사용, 방화벽 확인하는데도 사용 가능
    ```shell
    > curl [확인할려는 주소 전체]
    
    > curl http://도메인(ip):port
    > curl -v telnet://[ip]:[port] # curl의 파라미터로 telnet 가능
    ```
5. wget
    서버상에서 파일 다운로드 할때 주로 사용하지만, 방화벽 확인하는데도 사용 가능
    ```shell
    > wget [ip]:[port]
    ```
    
    
#### 🔨 리눅스 파일구조 복사
직접 반영을 할수 없는 경우 현업에게 소스 전달시, 수정파일 적용을 간결하게 하기 위해서 기존 파일 구조와 동일하게 폴더를 전달하는 경우가 있음.
```shell
> find [복사하고싶은 디렉토리 경로] -type d -exec mkdir [복사할 위치 경로]/{} \;
```

#### 🔨 실시간 시스템 상태 알아보기
```shell
> top
```
- 세부필드 정보
1. `PID` : 프로세스ID
2. USER : 프로세스 실행시킨 사용자 ID
3. PR : 프로세스의 우선순위
4. NI : NICE 값, 일의 NICE VALUE값으로 마이너스를 가지는 프로세스는 우선순위가 높음.
5. VIRT : 가상메모리 사용량(SWAP+RES)
6. RES : 현재 페이지가 상주하고 있는 크기(Resident Size)
7. SHR : 분할된 페이지, 프로세스에 의해 사용된 메모리를 나눈 메모리의 총합
8. S : 프로세스의 상태 (S - Sleeping, R - Running, W - Swapped out process, Z - Zombies)
9. %CUP : 프로세스가 사용하는 cpu의 사용율
10. %MEM : 프로세스가 사용하는 메모리의 사용율
11. TIME+ : 프로세스가 시작된 이후 경과된 총 시간
12. COMMAND : 실행된 명령어

- top 명령어 실행후
    - `shift + p` : cpu사용량이 큰 순서로 정렬
    - `shift + m` : 메모리 사용량이 큰 순서로 정렬
    - `shift + t` : 실행된 시간이 큰 순서로 정렬


#### 🔨 vi 에디터 잘쓰기
- `shift + g` : 맨 아래로 이동
- `/검색어` 입력후 n, N으로 앞뒤 이동
- `gg` : 맨위로 이동
- `-` : 줄의 맨 처음으로 이동












