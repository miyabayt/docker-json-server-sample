# docker-json-server-sample

## docker run

```bash
$ docker build -t docker-json-server .
$ docker run -it --rm --name docker-json-server -p 8080:3000 -v $PWD:/data docker-json-server
```

## crud

```bash
$ # create
$ curl -s X POST 'http://localhost:8080/users' \
-H 'Content-Type: application/json' \
-d '{
        "createdAt": "2022-06-23T01:19:50",
        "updatedAt": "2022-06-23T01:19:50",
        "version": 1,
        "firstName": "saburo",
        "lastName": "yamada",
        "email": "aaaa@bbbb.com",
        "tel": "0000000000"
    }'

$ # read
$ curl -s -X GET 'http://localhost:8080/users'

$ # update
$ curl -s -X PUT 'http://localhost:8080/users/1' \
-H 'Content-Type: application/json' \
-d '{
            "createdAt": "2022-06-23T01:19:50",
            "updatedAt": "2023-06-23T01:19:50",
            "version": 2,
            "id": 1,
            "firstName": "taro",
            "lastName": "yamada",
            "email": "test2@example.com",
            "tel": "09011112221"
    }'

$ # delete
$ curl -s -X DELETE 'http://localhost:8080/users/3'
```