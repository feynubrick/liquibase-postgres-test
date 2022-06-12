# 예제 실행 방법

[설치 링크](https://docs.liquibase.com/install/home.html)를 참조해서 `liquibase`를 설치합니다.
Docker도 설치되어 있어야 합니다.

`.env`에는 PostgreSQL 14.3 버전을 Docker로 구동하는데 필요한 환경변수가 미리 세팅되어 있습니다.
자세한 환경변수에 대한 설명은 [여기](https://hub.docker.com/_/postgres)에서 확인해주세요.

다음의 명령어들을 참고하시면 됩니다.

```bash
$ docker compose up -d # PostgreSQL 서버 띄우기
$ liquibase status # 연결 상태 확인
$ liquibase update-sql # DB에 적용할 때 사용할 SQL 문 확인
$ liquibase update # 위의 SQL 문 DB에 적용
```

# changelog 파일의 내용

파일의 내용은 Liquibase 문서에서 발췌한 내용입니다.
<https://docs.liquibase.com/concepts/changelogs/xml-format.html>

# changelog 폴더구조에 관해서

Liquibase에서 제시하는 [best practice](https://docs.liquibase.com/concepts/bestpractices.html)를 참고했습니다.
이중 주목할 만한 것은 `_root.xml`입니다.
`liquibase.properties`에 명시되었듯이 이 "update"에는 `_root.xml` 파일의 내용이 사용됩니다.
따라서 새 버전의 changelog 파일을 추가한다면 이 파일 역시 동일한 내용으로 덮어쓰기해야 합니다.
