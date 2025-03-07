# About this Release

WSO2 API Manager is a complete platform for building, integrating, and exposing your digital services as managed APIs in the cloud, on-premise, and hybrid architectures to drive your digital transformation strategy. It allows API developers to design, publish, and manage the lifecycle of APIs and API product managers to create API products from one or more APIs. APIs can be built by integrating different types of APIs such as traditional request-response style APIs and Event-driven APIs using a low-code/no-code development experience, and the APIs can be exposed to consumers through its API Gateway. 

For more information on WSO2 API Manager, see the [overview]({{base_path}}/getting-started/overview/).

The **WSO2 API Manager 4.1.0 Milestone 1 (M1)** is the latest **WSO2 API Manager release** and is the successor of **WSO2 API Manager 4.0.0**. It contains the following components, which have new features and enhancements:

## **API Manager**

The API Manager component addresses all aspects of API management in the platform. It consists of an API Gateway, API Publisher, Developer Portal, Key Manager, and Traffic Manager.

<table>
<tr>
<td>
API Manager 4.1.0-M1</td>
<td><a href="https://github.com/wso2/product-apim/releases/download/v4.1.0-m1/wso2am-4.1.0-m1.zip">download</a></td>
</tr>
</table>

### New features

-  **[PKCE Support]({{base_path}}/consume/manage-application/generate-keys/generate-api-keys/#generating-application-keys-with-pkce-enabled/) (M1)**
  
     WSO2 API Manager supports Proof Key for Code Exchange (PKCE) when generating application keys. This is a security measure to secure the applications that are executing in the same domain.

- **[Ability to configure Rate Limiting for an API Gateway Cluster]({{base_path}}/design/rate-limiting/advanced-topics/configuring-rate-limiting-api-gateway-cluster/) (M2)**

     Ability to configure Rate Limiting for an API Gateway Cluster via the Redis server so that the request counters maintained for burst control and backend rate limiting will be replicated across the API Gateway cluster when working with multiple API Gateway nodes.

### Improvements

- **Authentication for Prototype APIs (M1)**

	 Authentication for Prototype APIs is available by default so that the client apps can also be created using authentication to test out the APIs. If needed you can [disable authentication for Prototype APIs]({{base_path}}/design/prototype-api/create-a-prototype-api/)) at the resource level or API level.

<! --- ### Deprecated features and functionalities

<! --- The support for these features will be removed from subsequent versions starting from WSO2 API Manager 4.1.0.

<! --- ### Removed features and functionalities

<! --- These features are unsupported and removed from WSO2 API Manager 4.1.0 onwards.

<! --- ### Key changes --->

## **Micro Integrator**

The Micro Integrator is a cloud-native, standards-based messaging engine and an integration framework with a configuration-based runtime environment for integrating APIs, services, data, SaaS, proprietary, and legacy systems.

This serves the integration needs for the data plane of the API Manager platform.

<table>
<tr>
<td>Micro Integrator  4.1.0-M1</td> 
<td><a href="https://github.com/wso2/micro-integrator/releases/download/v4.1.0-m1/wso2mi-4.1.0-m1.zip">download</a></td>
</tr>
</table>

### New features

-  **[Exposing an Integration SOAP Service as a Managed API]({{base_path}}/tutorials/integration-tutorials/service-catalog-tutorial-for-proxy-services/) (M1)**

     WSO2 API Manager includes a Service Catalog where developers can register their backend services as Managed APIs. Through the Service Catalog, now SOAP integration services are made discoverable to the API Management layer so that SOAP PassThrough API proxies can directly be created using them.

- **[Audit Log support]({{base_path}}/observe/micro-integrator/classic-observability-logs/monitoring-mi-audit-logs) (M1)**

  	 The Audit Log capability allows you to add logging for the Micro Integrator Management API. Maintaining Audit Logs allows you to identify the changes that took place in the Micro Integrator instance and also to identify as to who made those changes.

- **[File Inbound Endpoint Sub Directory Processing Capability]({{base_path}}/reference/synapse-properties/inbound-endpoints/polling-inbound-endpoints/file-inbound-endpoint-properties) (M1)**

     VFS Inbound Endpoints are capable of handling files inside sub-directories of the specified URL. This enables users to process files recursively inside a directory.

## **Streaming Integrator**

Streaming Integrator serves the streaming-based integrations and acts as the event stream provider for Streaming APIs in the data plane of the API Manager platform.

<table>
<tr>
<td>Streaming Integrator  4.1.0-M1</td> 
<td><a href="https://github.com/wso2/streaming-integrator/releases/download/v4.1.0-m1/wso2si-4.1.0-m1.zip">download</a>
</td> 
</tr>
</table>

### New features

- **Add support for SMB and WebDAV protocols**

     This feature adds support to read from or write to files opened via SMB and WebDAV protocols.

### Improvements

- Improved CDC functionalities

- Improved MongoDB store 

## **API Controller (apictl)**

WSO2 API Controller (apictl) is a command-line tool providing the capability to move APIs, API Products, and Applications across environments and to perform CI/CD operations. It can also be used to perform these same tasks on a Kubernetes deployment. In addition, apictl can be used as a developer CLI tool for Choreo Connect. Furthermore, it can perform Micro Integrator server-specific operations such as monitoring Synapse artifacts and performing MI management/administrative tasks from the command line.

<table>
<tr>
<td>API Controller 4.1.0-M1</td>
<td><a href="https://github.com/wso2/product-apim-tooling/releases/tag/v4.1.0-m1">download</a></td>
</tr>
</table>

<! --- ### New features--->

### Improvements

- The list of improvements are available [here](https://github.com/wso2/product-apim-tooling/issues?q=is%3Aissue+label%3A4.1.0+is%3Aclosed+label%3A%22Type%2FImprovement%22+).

## **WSO2 Integration Studio**

WSO2 Integration Studio is an open-source development environment used to design and develop integration scenarios for WSO2 Micro Integrator. 

<table>
<tr>
<td>Integration Studio  8.1.0-M1</td>
<td><a href="https://github.com/wso2/integration-studio/releases/tag/v8.1.0-m1">download</a></td>
<tr>
</table>

### New features

- **[Auto-generation support for data services using a given data source]({{base_path}}/integrate/develop/creating-artifacts/data-services/creating-data-services/#generate-data-service-from-a-datasource) (M1)**

     This feature allows you to generate data service definitions by pointing to an existing datasource in the workspace without creating that from scratch.

- **[Exposing proxy services via Service Catalog for WSO2 APIM]({{base_path}}/integrate/develop/generate-service-catalog-metadata) (M1)**

     This feature generates metadata artifacts for the APIs and Proxy services that have been created inside the older Integration Studio workspaces.

- Integrated APIM Tooling into Integration Studio (M1)

### Improvements

- Capability to generate metadata files for APIs and Proxy services for older ESB projects (M1).

- HTTPS support for unit tests of APIs (M1)

- Option to hide/show connectors on-demand (M1)

- JSON and YAML templates as registry resources (M1)

## **Micro Integrator Dashboard**

The Micro Integrator dashboard can connect to multiple Micro Integrator server instances and monitor artifacts and logs from a selected cluster or group of server nodes.

<table>
<tr>
<td>Micro Integrator Tooling  4.1.0-M1</td>
<td><a href="https://github.com/wso2/micro-integrator/releases/download/v4.1.0-m1/wso2mi-dashboard-4.1.0-m1.zip">download</a></td>
<tr>
</table>

### New features

- **[Single Sign-on with OpenID Connect]({{base_path}}/install-and-setup/install/installing-the-product/running-the-mi-dashboard/#configuring-single-sign-on-with-openid-connect)**

     Users can use OIDC based Single Sign-On to log in to the WSO2 Micro Integrator Monitoring Dashboard.

## **Streaming Integrator Tooling**

The Streaming Integrator Tooling is a developer tool to develop Siddhi applications and simulate events for testing purposes.

<table>
<tr>
<td>Streaming Integrator Tooling  4.1.0-M1</td>
<td><a href="https://github.com/wso2/streaming-integrator-tooling/releases/download/v4.1.0-m1/wso2si-tooling-4.1.0-m1.zip">download</a></td>
</tr>
</table>

## New Features

- Support for SMB and WebDAV file protocols (M1)

## Improvements

- Improved CDC functionalities.

<!-- Hiding coz there was noting new for M1
## Choreo Connect

The Choreo Connect is a lightweight gateway for APIs. It is used for message security, transport security, routing, and other common API Management related quality of services. It can collect information required for usage metering and throttling capabilities. The Choreo Connect natively supports scaling in highly decentralized environments including microservice architecture.

<! --- #### New features --->

<!-- Hiding coz there was noting new for M1
## **Kubernetes API Operator**

Microservices are increasingly being deployed on Kubernetes. As a result, it is important to expose these microservices as well documented, easy to consume, managed APIs so that they can be used to develop great applications. The API operator for Kubernetes makes APIs a first-class citizen in the Kubernetes ecosystem. Similar to deploying microservices, you can now use this operator to deploy APIs for individual microservices or compose several microservices into individual APIs. With this, users can expose their microservice as managed APIs in the Kubernetes environment without any additional work.

The API operator for Kubernetes provides first-class support for Micro Integrator deployments in the Kubernetes ecosystem. It uses the Integration custom resource (`integration_cr.yaml` file) that is available in the Kubernetes project (exported from WSO2 Integration Studio) and deploys the integration in your Kubernetes environment.

It is now available to download from [here](https://github.com/wso2/k8s-api-operator/releases/).
K8s API Operator v2.0.0 is compatible with API Manager v4.0.0.

<! --- ### New features --->

## **Compatible WSO2 product versions**

WSO2 API Manager 4.1.0 is based on WSO2 Carbon 4.6.1 and is expected to be compatible with any of the WSO2 products that are based on any Carbon 4.6.x version. If you encounter any compatibility issues, please [contact team WSO2](http://wso2.com/support/). For more information on the products in each Carbon platform release, see the [Release Matrix](http://wso2.com/products/carbon/release-matrix/).

<hr style="border:8px solid gray"> </hr>

## **Fixed and known issues**

**API Manager**

- Fixed Issues - See [details of all the changes including improvements, and bug fixes in this release](https://github.com/wso2/product-apim/issues?q=is%3Aissue+milestone%3AAPIM-4.1.0-M1+is%3Aclosed+).

- Known Issues - All the open issues pertaining to WSO2 API Manager 4.1.0 are reported [here](https://github.com/wso2/product-apim/issues?q=is%3Aopen+is%3Aissue+label%3A4.x.x).

**Micro Integrator**

- Fixed Issues - See [details of all the changes including improvements, and bug fixes in this release](https://github.com/wso2/micro-integrator/milestone/25?closed=1).

- Known Issues - All the open issues pertaining to WSO2 API Manager 4.1.0 are reported [here](https://github.com/wso2/micro-integrator/issues?q=is%3Aopen+is%3Aissue).

**Streaming Integrator**

- Fixed Issues - See [details of all the changes including improvements, and bug fixes in this release](https://github.com/wso2/streaming-integrator/milestone/17?closed=1).

- Known Issues - All the open issues pertaining to WSO2 API Manager 4.1.0 are reported [here](https://github.com/wso2/streaming-integrator/issues?q=is%3Aopen+is%3Aissue).

**API Controller**

- Fixed Issues - See [details of all the changes including improvements, and bug fixes in this release](https://github.com/wso2/product-apim-tooling/milestone/11?closed=1).

- Known Issues - All the open issues pertaining to WSO2 API Manager 4.1.0 are reported [here](https://github.com/wso2/product-apim-tooling/issues?q=is%3Aopen+is%3Aissue).

**Integration Studio**

- Fixed Issues - See [details of all the changes including new features, improvements, and bug fixes in this milestone release](https://github.com/wso2/integration-studio/milestone/11?closed=1).

- Known Issues - All the open issues pertaining to WSO2 Integration Studio are reported [here](https://github.com/wso2/integration-studio/issues?q=is%3Aopen+is%3Aissue).

**Micro Integrator Dashboard**

- Fixed Issues - See [details of all the changes including new features, improvements, and bug fixes in this release](https://github.com/wso2/product-mi-tooling/milestone/1?closed=1).

- Known Issues - All the open issues pertaining to WSO2 Integration Studio are reported [here](https://github.com/wso2/product-mi-tooling/issues?q=is%3Aopen+is%3Aissue).

**Streaming Integrator Tooling**

- Fixed Issues - See [details of all the changes including improvements, and bug fixes in this release](https://github.com/wso2/streaming-integrator/milestone/17?closed=1).

- Known Issues - All the open issues pertaining to WSO2 API Manager 4.1.0 are reported [here](https://github.com/wso2/streaming-integrator-tooling/issues?q=is%3Aopen+is%3Aissue).

**Choreo Connect**

- Fixed Issues - See [details of all the changes including improvements, and bug fixes in this release]()
- Known Issues - All the open issues are reported [here](https://github.com/wso2/product-microgateway/issues?q=is%3Aopen+is%3Aissue+label%3Aenvoy-gw).

**Kubernetes API Operator**

- Fixed Issues - See [details of all the changes including improvements, and bug fixes in this release]().

- Known Issues - All the open issues pertaining to WSO2 API Manager 4.1.0 are reported [here]().
