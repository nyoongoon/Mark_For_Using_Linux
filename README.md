# Mark_For_Using_Linux
리눅스를 사용하면서 기억할만한 것들을 기록합니다.

Ver 14.14 Distrib 5.7.34<br>5.7.34-0ubuntu0.18.04.1

<br>

# Based on Linux File System
<br>

## /var
- 설정 -> /etc/mysql/mysql.conf.d
- 일반 로그 -> /var/lib/mysql/ip-172-31-4-95.log 

<br>

---

---

<br>

# Based on Application
<br>

## Mysql
- 설정 -> /etc/mysql/mysql.conf.d
- 일반 로그 -> /var/lib/mysql/ip-172-31-4-95.log 

### Mysql 에러
- mysql 서버에 접속 할 경우 IP정보를 hostname으로 변환 해주는 DNS질의를 진행 합니다.
   
      이때 /etc/resolv.conf에 설정된 DNS정보가 올바르게 설정 되지 않아, 접속 지연 현상이 발생 하며, 간혹 첨부된 로그와 같이 mysqld이 종료 되는 현상이 발새 합니다.
      이런 경우 아래와 같은 설정으로 해당 문제를 해결 할수있습니다.

      1. my.cnf 파일에 추가 
      - skip-name-resolve

      2. mysqld 데몬 재구동
      - /usr/local/mysql/bin/mysqld_safe restart

      3. 설정 조회
      - mysql> SHOW VARIABLES LIKE 'skip_name_resolve';
      +-------------------+-------+ 
      | skip_name_resolve | ON    | 
      +-------------------+-------+

