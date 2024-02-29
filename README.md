# R3-nGrinder

![image](https://github.com/be01-4nd-mini-project-TEAM1/R3-nGrinder/assets/148875683/54eae3a9-7dc6-4fa6-9cbc-8f8ca7d066b4)
## nGrinder 설치 
- https://github.com/naver/ngrinder/releases
```
$ wget https://github.com/naver/ngrinder/releases/download/ngrinder-3.5.2-20200929/ngrinder-controller-3.5.2.war
$ java -jar ngrinder-controller-{version}.war
```
### nGrinder Controller Port-Forwarding
- 다른 PC에서 사설 IP로 컨트롤러 PC에 접속하기 위한 세팅
- 윈도우 터미널에서 관리자 권한으로 실행 후 다음과 같이 입력
```sh
$ netsh interface portproxy add v4tov4 listenport=8080 listenaddress=0.0.0.0 connectport=8080 connectaddress=[WSL 할당 IP]
```
- 사설 IP의 8080 포트로 실행된 Controller 페이지 진입 확인


### AGENT setting
- controller ip:지정 Port 로 접속 후 agent tar download

![image](https://github.com/be01-4nd-mini-project-TEAM1/R3-nGrinder/assets/102152330/89997bce-899e-408e-ba10-d69d095a89c4)

- 다운로드한 tar 압축 해제
```
$ tar -xvf [agent tar file]
```

- __agent.conf file setting
```
$ cd ngrinder-agent
$ vi __agent.conf
common.start_mode=monitor
agent.controller_host=192.168.0.43
monitor.binding_port=13243
```

- run agent server
```
./run_agent.sh
```

- agent 접속 확인

![image](https://github.com/be01-4nd-mini-project-TEAM1/R3-nGrinder/assets/102152330/e2a7f4a4-fe74-4dc3-841f-732087ae7944)

