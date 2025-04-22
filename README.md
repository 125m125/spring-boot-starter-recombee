# Spring Boot Integration for Recombee API Client

Spring Boot 2 and 3 Integration for the [Recombee Java API Client](https://github.com/recombee/java-api-client).

It provides a starter that includes the api-client and an AutoConfiguration to create automatically create a RecombeeClient Bean based on the configuration in the properties.

## Installation and Usage

Add the following `<dependency>` entry to your project's POM. For Spring Boot 2, use the following:

```xml
    <dependency>
        <groupId>de.125m125.recombee</groupId>
        <artifactId>api-client-spring-boot-2-starter</artifactId>
        <version>5.0.0</version>
    </dependency>
```

For Spring Boot 3, use the following:

```xml
	<dependency>
		<groupId>de.125m125.recombee</groupId>
		<artifactId>api-client-spring-boot-3-starter</artifactId>
		<version>5.0.0</version>
	</dependency>
```

For the automatic configuration of the bean, you need to add the following properties:

```yaml
com.recombee.client.database-id=my-database-id
com.recombee.client.token=db-private-token
com.recombee.client.region=US_WEST
```
Afterwards, if autoconfiguration is enabled, an instance of RecombeeClient will automatically be created and you can inject it into your components:
```java
import com.recombee.api_client.RecombeeClient;

@Component
public class SampleComponent {
	
	private final RecombeeClient client;
	
	public SampleComponent(RecombeeClient client) {
		this.client = client;
	}
}
```

See the [Recombee Java API Client](https://github.com/recombee/java-api-client) for detailed usage of the client.