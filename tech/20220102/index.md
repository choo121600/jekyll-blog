---
layout: post
type: tech
date: 2022-01-02 02:56
category: Backend
title: dotenv를 이용한 Config 설정
tech-header: true
hash-tag: [Config, Backend]
---


일반적으로 서비스를 개발 할 때 로컬 또는 개발자 PC환경에서 개발과 테스트를 하고<br>
개발한 코드를 스테이지 서버라고 부르는 테스트 환경에 배포하여 통합테스트를 진행한다.<br>
이후 테스트 서버환경에서 문제가 없다면 다시 production서버로 배포하는 과정을 거친다.<br>
<br>
이렇게 실행환경이 달라지게 되는데 실행환경에 따라 달라지는 변수들이 있습니다.<br>
따라서 환경에 따라 바뀌는 이 값들에 맞게 각 환경의 DB에 연결하기 위한 코드를 따로 작성해야 하는 것은 매우 비효율적이다.<br>
<br>
이 문제를 해결하기 위해 nodejs 라이브러리에 dotenv라는 라이브러리가 있다.<br>
각 환경에 따라 바뀐느 변수를 ```.env```확장자를 가진 파일에 저장해 두고 서버가 구동 될 떄 이 파일을 읽어 환경변수로 설정해주는 역할을 한다.<br>
<br>
```
$ yarn add dotenv
```

index.js
```javascript
const dotenv = require("dotenv");

dotenv.config({ path: "./.env" })

const connection = mysql.creatConnection({
    host: process.env.DB_HOST,
    user: proecss.env.DB_USER,
    password: process.env.DB_PASSWORD,
    database: process.env.DB_NAME
})
```

.env
```
DB_name = dbName
DB_password = password
DB_user = userName
DB_host = localhost
```

각 .env 파일은 소스코드 저장소에서 모두 관리하고 구동될 때 환경에 맞는 .env파일을 읽도록 처리해야한다. <br>
환경변수는 다음 명령어로 설정하거나 os가 구동될 때 변수를 설정해야 한다.<br>
<br>
소스코드 내에 적어두면 안되는 변수는 서버가 구동될 때 환경변수로 설정한다.<br>
