# Event Hub

The Event Hub acts as a mediator between the adapter and the control plane. Choreo Connect uses the below methods to fetch data from API Manager.

- Internal Data REST API
- JMS Topic

!!! note
    The event hub is included within the control plane profile of APIM. Therefore, if you use a distributed setup use the IP address of the control plane node for the configurations. Refer [API-M Profiles]({{base_path}}/install-and-setup/setup/distributed-deployment/product-profiles) for more information on profiles.

## Internal Data REST API

The Internal Data API (```https://<APIM_HOST>:<PORT>/internal/data/v1```) is a REST API exposed in WSO2 API Manager to retrieve data related to APIs, applications, subscriptions, key managers, throttling and token revocation. 

During the startup, Choreo Connect invokes this API to fetch the already created API, application, subscription, key manager, throttling, revoked token data for authenticated users tenant domain.

## JMS Topic

Choreo Connect has several consumers such as notification, keymanager, token revocation and throttling which are subscribed with relevant topics in order to receive events from 
Control Plane. By enabling the Control Plane Event Hub in the Choreo Connect configuration file,
the real time data in WSO2 API Manager will automatically be available in Choreo Connect.

### Notification events
When a create/remove/an update operation happens for an API, application or subscription in API Manager, the data are published to notification JMS topic. When the event is received to notification consumer, Choreo Connect update the in-memory data stores related to APIs, Applications and Subscriptions.

### KeyManager events
When a create/remove/an update operation happens for the keyManagers resides on APIM admin portal, the data are published to Keymanager JMS topic. When the event is received to keymanager consumer, Choreo Connect update the in-memory token issuer data store. 

!!! note
    The update in token issuer data store happen for remove keymanager only if that issuer is not presented in security token service configuration.


## Setting the Connection for JMS receiver

Multiple event listening endpoints can be defined as an array to use for the connection, along with optional failover parameters. 

Sample configuration for `eventListeningEndpoints` for JMS receiver can be defined as follows.
```toml
[controlPlane.brokerConnectionParameters]
    eventListeningEndpoints = ["amqp://admin:$env{cp_admin_pwd}@apim:5672?retries='10'&connectdelay='30'",
                               "amqp://admin:$env{cp_admin_pwd}@apim:5673?retries='20'&connectdelay='30'"]
```

| Optional parameters| Default Value| Description|
|-----------|-----------|----------|
|`retries`  | 1 |The number of retry attempts when connecting to the broker.|
|`connectdelay`  | None | How long (in seconds) to wait before attempting to reconnect. The recommended value is 30 seconds.|


### Event Hub Configuration

 ``` toml
 [controlPlane]
  enabled = true
  serviceUrl = "https://<apim-ip>:9443/"
  username="admin"
  password="$env{cp_admin_pwd}"
  environmentLabels = ["Default"]
  retryInterval = 5
  skipSSLVerification=true

  [controlPlane.brokerConnectionParameters]
    eventListeningEndpoints = ["amqp://admin:$env{cp_admin_pwd}@<apim-ip>:5672?retries='10'&connectdelay='30'"]
    reconnectInterval = 5000
    reconnectRetryCount = 60

  [controlPlane.httpClient] 
    requestTimeOut = 30
 ``` 
