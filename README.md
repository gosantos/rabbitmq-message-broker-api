# rabbitmq-message-broker-api

- A Spring Boot API integrated with RabbitMQ message broker to deal with message objects;
- A quick/soft API that receives requests (fictional payment approach) and delegates it in a message format to a RabbitMQ broker.

### Prerequisites

* [Java](https://sdkman.io/install)
* [Docker](https://docs.docker.com/get-docker/)

### Executing

```
$ git clone https://github.com/lucasmnunes/rabbitmq-message-broker-api.git
$ docker-compose up
```

### Using

After doing the steps above, curl is your friend:

```
$ curl -v --header "Content-Type: application/json" \
  --request POST \
  --data '{"id":"f42a289dasdas8-12dsad4f-4841-a466-a25ac2bfcd06","description":"ebc13dsdsaadsa9c7-c5c3-44df-af91-27a7dsa64sdadsa154813","option":"CREDIT_CARD","price":12.35,"quantity":10,"status":"COMPLETED"}' \
  http://localhost:8080/payment-api/api/v1/payments
```

### Result

- After doing the steps above, the message should be in RabbitMQ it (waiting for consumers);
- You can check it by accessing the management and monitoring RabbitMQ interface: http://localhost:15672/ (the default username/password is guest/guest);
- To access the management/monitoring interface, check out the docs: https://www.rabbitmq.com/management.html.

