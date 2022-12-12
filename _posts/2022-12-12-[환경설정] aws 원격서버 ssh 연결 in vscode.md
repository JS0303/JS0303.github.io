# [환경설정] aws 원격서버 ssh 연결 in vscode

1. VScode에서 Remote - SSH Extension 설치
2. ‘command + shift + p’ 를 통해 config 파일 선택
3. 다음 포맷을 통해 원격 서버의 정보 입력
    
    ```
    Host [alias]
    	HostName [ip addr]
    	User [account_name]
    	Port [port number]
    	IdentityFile [key location]
    ```
    
4. 다시 ‘command + shift + p’를 통해 Host 선택
5. 연결 완료