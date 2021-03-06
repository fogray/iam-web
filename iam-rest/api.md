# API 说明

###1. 创建Account
 POST /api/v1/accounts

```
{
    "email":"123456@163.com",
    "password":"123456",
    "status":"enabled",
    "username":"Lion"
}
```
```
curl -H 'Content-Type: application/json' -XPOST https://dev.imaicloud.com/iam/api/v1/accounts \
-d '{ "email":"wbwang@inspur.com",   "password":"123",  "status":"enabled",  "username":"wbwang" }'
```


###2. 创建用户组Group

POST /api/v1/groups

```
{
    "name":"Group A",
    "description":"Test Group",
    "status":"enabled"
}
```

###3. 将Account添加到Group

POST /api/v1/groupMemberships

```
{
    "account":"PYuMRmTSTvCltqHIHoAZ2A",
    "group":"7sY39nbxQpSGxFdt6Yeu2Q"
}
```

###4. Account的附属资源customData

Account创建过程会同时创建customData，其中的定制数据为空

####4.1 访问Account的customData

GET /api/v1/accounts/$ACCOUNT_ID/customData

curl https://dev.maicloud.com/iam/api/v1/accounts/$ACCOUNT_ID/customData

####4.2 定制cusotmData数据

(POST https://dev.imaicloud.com/iam/api/v1/accounts/$ACCOUNT_ID/customData)

POST /api/v1/accounts/$ACCOUNT_ID/customData

```
{
	"permission":"A"
}
```
```
export ACCOUNT_ID=YykNiKy9Tpqa93Q0hh0gWg
curl -H 'Content-Type: application/json' -XPOST https://dev.imaicloud.com/iam/api/v1/accounts/$ACCOUNT_ID/customData -d '{ "permission":"A" }'
```
