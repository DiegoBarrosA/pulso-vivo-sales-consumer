# pulso-vivo-sales-consumer

Este microservicio Java Spring Boot consume mensajes de la cola RabbitMQ `stock-changes` y los inserta en la tabla `SALE_STOCK_CHANGE` de Oracle Cloud usando un wallet.

## Configuración

1. **RabbitMQ**: Ajusta los parámetros de conexión en `src/main/resources/application.properties` si es necesario.
2. **Oracle Wallet**: Coloca los archivos del wallet en `src/main/resources/wallet`.
3. **Credenciales**: Configura usuario y contraseña de Oracle en `application.properties`.

## Ejecución

```bash
mvn clean package
java -jar target/sales-consumer-0.0.1-SNAPSHOT.jar
```

## Formato del mensaje consumido

```json
{
  "productId": 1,
  "productName": "Laptop Dell XPS 13",
  "productCategory": "Electronics",
  "quantityChanged": 2,
  "newQuantity": 23,
  "saleTotal": 2599.98,
  "changeTimestamp": [2025,6,29,0,20,39,902970229]
}
```
