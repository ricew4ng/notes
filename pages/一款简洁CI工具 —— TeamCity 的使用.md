-
- 编辑内部变量
- Administration > Diagnostics > Internal Properties
-
- 在Command Line中
- %var% 表示 Configuration Parameter
- $var 表示 Env Parameter
-
### API 介绍
- https://www.jetbrains.com/help/teamcity/rest/start-and-cancel-builds.html#Start+custom+build
-
- curl --location --request POST 'http://10.92.20.43:8111/app/rest/buildQueue' \
  --header 'Authorization: Bearer eyJ0eXAiOiAiVENWMiJ9.ZXlWanNIckpoTDZ6SElpeXQ5cXJIZ0hKZ3dB.NGJhYzQxYWEtZWQ3NC00YTljLTg0ZjUtYzJmODYxYzNhYWRj' \
  --header 'Origin: http://10.92.20.43:8111' \
  --header 'Content-Type: application/json' \
  --header 'Cookie: TCSESSIONID=8AAE0E6B776E34C551751A871578213B' \
  --data-raw '{
      "buildTypeId": "OpsApi_Pipeline",
      "branchName": "dev-wwq",
      "properties": {
          "property": [
              {"inherited": false, "name": "dev", "value": "10.2.24.103", "type": {"rawValue": "rawValue"}}
          ]
      }
  }'
-
### TeamCity 数据库迁移
-