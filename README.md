# Docker mariadb install
'''
docker pull mariadb
docker run -p 3306:3306 --name mariadb --restart=always -e MARIADB_ROOT_RASSWORD={비밀번호} -d mariadb
'''

 * -p 3306:3306: 호스트와 컨테이너의 포트를 연결 호스트:컨테이너
 * --name mariadb: 컨테이너의 이름을 명명한다. 
 * -e MARIADB_ROOT_PASSWORD: 환경변수 설정 
 * -d: 백그라운드 모드로 실행
 * --restart=always: 도커가 실행되면 이 컨테이너도 실행되도록 설정


## 컨테이너에 적속해서 사용자 추가하기
'''
docker exec -it mariadb /bin/bash

mysql -u root -p
> USE mysql;
> CREATE USER '{사용자 이름}'@'%' IDENTIFIED BY '{비밀번호}';
> GRANT ALL PRIVILEGES ON *.* TO '{사용자 이름}'@'%';
> FLUSH PRIVILEGES;
'''

 
