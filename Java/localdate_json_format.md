Java 8's LocalDate Field to Json Format

```java
@JsonFormat(pattern = "yyyy-MM-dd HH:mm:ss")
@JsonDeserialize(using = LocalDateDeserializer.class)
@JsonSerialize(using = LocalDateSerializer.class)
private LocalDate updateDate;
```
