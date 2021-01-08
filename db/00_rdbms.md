# 00. RDBMS

## oracleDB 연습

- docker 설치 
  `brew install --cask docker`

- oracle 설치
  `docker search oracle-xe-11g`

  `docker pull jaspeen/oracle-xe-11g`

  `docker run --name oracle -d -p 8080:8080 -p 1521:1521 jaspeen/oracle-xe-11g`

- SQLPlus 실행하기
  `docker exec -it oracle sqlplus`
  user-name : system

  password : oracle

- Oracle SQL Developer 설치

  - https://www.oracle.com/kr/tools/downloads/sqldev-v192-downloads.html OS에 맞는 파일 다운로드

  - 압출 풀고 실행

    - 자바 버전 문제로 실행 안될 때 자바 8 이상 설치,
       혹은 높을 경우

      ```bash
      vi /Applications/SQLDeveloper.app/Contents/MacOS/sqldeveloper.sh
      ```

      가서

      ```bash
      TMP_PATH=`/usr/libexec/java_home -F -v 9`
      ```

      를

      ```bash
      TMP_PATH=`/usr/libexec/java_home -F -v 10`
      ```

      자기 버전에 맞게 변경

- 오라클 hr 계정 해제

  run sql

  `connect system/admin` -> connected

  `ALTER USER hr ACCOUNT UNLOCK;` oracle hr unlock

  `ALTER USER hr IDENTIFIED BY hr/hr;` hr의 pw를 hr로 설정

  `connect hr/hr`

