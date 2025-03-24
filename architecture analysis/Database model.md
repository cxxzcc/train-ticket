## Database model

### mongodb

#### ts-train-mongo

```java
ts-train-service
@Document(collection="trainType")
public class TrainType {
    @Valid
    @Id
    private String id;
    @Valid
    private int economyClass;
    @Valid
    private int confortClass;
    private int averageSpeed;
```

#### ts-inside-payment-mongo

```java
ts-inside-payment-service
@Document(collection="addMoney")
public class AddMoney {

    @Valid
    @NotNull
    @Id
    private String id;

    @Valid
    @NotNull
    private String userId;

    @Valid
    @NotNull
    private String money;

    @Valid
    @NotNull
    private AddMoneyType type;
}
public enum AddMoneyType implements Serializable {
    A("Add Money",1),D("Draw Back Money",2);

    private String name;
    private int index;
}

@Document(collection="payment")
public class Payment {
    @Id
    @NotNull
    @Valid
    private String id;

    @NotNull
    @Valid
    private String orderId;

    @NotNull
    @Valid
    private String userId;

    @NotNull
    @Valid
    private String price;

    @NotNull
    @Valid
    private PaymentType type;
}
public enum  PaymentType implements Serializable {
    P("Payment",1), D("Difference",2),O("Outside Payment",3),E("Difference & Outside Payment",4);

    private String name;
    private int index;
}
```

#### ts-config-mongo

```java
ts-config-service
@Document(collection="config")
public class Config {
    @Valid
    @Id
    @NotNull
    private String name;

    @Valid
    @NotNull
    private String value;

    @Valid
    private String description;
```



#### ts-payment-mongo

```java
ts-payment-service
@Document(collection="addMoney")
public class AddMoney {
    private String userId;
    private String money;
}
@Document(collection="payment")
public class Payment {
    @Id
    @NotNull
    @Valid
    private String id;

    @NotNull
    @Valid
    private String orderId;

    @NotNull
    @Valid
    private String userId;

    @NotNull
    @Valid
    private String price;
}
```



#### ts-price-mongo

```java
ts-price-service
@Document(collection="price_config")
public class PriceConfig {

    @Id
    private UUID id;

    private String trainType;

    private String routeId;

    private double basicPriceRate;

    private double firstClassPriceRate;
    
```



#### ts-station-mongo

```java
ts-station-service
@Document(collection="station")
public class Station {
    @Valid
    @NotNull
    @Id
    private String id;

    @Valid
    @NotNull
    private String name;

    private int stayTime;
```



#### ts-travel-mongo

```java
ts-travel-service
@Document(collection="trainType")
public class TrainType {
    @Valid
    @Id
    private String id;

    @Valid
    private int economyClass;

    @Valid
    private int confortClass;

    private int averageSpeed;
}
@Document(collection="trip")
public class Trip {
    @Valid
    @Id
    private TripId tripId;

    @Valid
    @NotNull
    private String trainTypeId;

    private String routeId;

    private Date startingTime;

    @Valid
    @NotNull
    private String startingStationId;

    @Valid
    private String stationsId;

    @Valid
    @NotNull
    private String terminalStationId;



    @Valid
    @NotNull
    private Date endTime;
```

#### ts-travel2-mongo

```java
ts-travel2-service
@Document(collection="trainType")
public class TrainType {
    @Valid
    @Id
    private String id;

    @Valid
    private int economyClass;
    @Valid
    private int confortClass;

    private int averageSpeed;
}
@Document(collection="trip")
public class Trip {
    @Valid
    @Id
    private TripId tripId;

    @Valid
    @NotNull
    private String trainTypeId;

    private String routeId;


    @Valid
    @NotNull
    private String startingStationId;

    @Valid
    private String stationsId;

    @Valid
    @NotNull
    private String terminalStationId;

    @Valid
    @NotNull
    private Date startingTime;

    @Valid
    @NotNull
    private Date endTime;
```

### mysql

#### ts-voucher-mysql

```mysql
CREATE TABLE `voucherservice`.`voucher` (
  `voucher_id` INT NOT NULL AUTO_INCREMENT,
  `order_id` VARCHAR(1024) NOT NULL,
  `travelDate` DATE NOT NULL,
  `travelTime` VARCHAR(1024) NOT NULL,
  `contactName` VARCHAR(1024) NOT NULL,
  `trainNumber` VARCHAR(1024) NOT NULL,
  `seatClass` INT NOT NULL,
  `seatNumber` VARCHAR(1024) NOT NULL,
  `startStation` VARCHAR(1024) NOT NULL,
  `destStation` VARCHAR(1024) NOT NULL,
  `price` FLOAT NOT NULL,
  PRIMARY KEY (`voucher_id`));
```

