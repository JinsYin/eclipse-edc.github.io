---
 title: Connector
 weight: 10
---

EDC Autodoc Manifest
====================

Module `org.eclipse.edc:accesstokendata-store-sql:0.9.0`
--------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.store.sql.SqlAccessTokenDataStoreExtension`
**Name:** "Sql AccessTokenData Store"

**Overview:**  Provides Sql Store for {@link AccessTokenData} objects



##### Configuration: 

| Key                                        | Required | Type     | Default   | Pattern | Min | Max | Description                                                  |
| ------------------------------------------ | -------- | -------- | --------- | ------- | --- | --- | ------------------------------------------------------------ |
| ~~edc.datasource.accesstokendata.name~~    |          | `string` | ``        |         |     |     | Name of the datasource to use for accessing data plane store |
| `edc.sql.store.accesstokendata.datasource` |          | `string` | `default` |         |     |     | The datasource to be used                                    |

##### Provided services:
- `org.eclipse.edc.connector.dataplane.spi.store.AccessTokenDataStore`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.connector.dataplane.store.sql.schema.AccessTokenDataStatements` (optional)
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper` (required)

Module `org.eclipse.edc:api-core:0.9.0`
---------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.api.ApiCoreDefaultServicesExtension`
**Name:** "ApiCoreDefaultServicesExtension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationRegistry`
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationProviderRegistry`

##### Referenced (injected) services:
_None_

#### Class: `org.eclipse.edc.api.ApiCoreExtension`
**Name:** "API Core"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry` (required)

Module `org.eclipse.edc:api-observability:0.9.0`
------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.api.observability.ObservabilityApiExtension`
**Name:** "Observability API"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.spi.system.health.HealthCheckService` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.spi.system.apiversion.ApiVersionService` (required)

Module `org.eclipse.edc:asset-api:0.9.0`
----------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.api.management.asset.AssetApiExtension`
**Name:** "Management API: Asset"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.asset.AssetService` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)

Module `org.eclipse.edc:asset-index-sql:0.9.0`
----------------------------------------------

_Categories: None_

### Extension points
  - `org.eclipse.edc.connector.controlplane.store.sql.assetindex.schema.AssetStatements`

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.store.sql.assetindex.SqlAssetIndexServiceExtension`
**Name:** "SQL asset index"

**Overview:** No overview provided.


##### Configuration: 

| Key                              | Required | Type     | Default   | Pattern | Min | Max | Description               |
| -------------------------------- | -------- | -------- | --------- | ------- | --- | --- | ------------------------- |
| `edc.sql.store.asset.datasource` |          | `string` | `default` |         |     |     | The datasource to be used |

##### Provided services:
- `org.eclipse.edc.connector.controlplane.asset.spi.index.AssetIndex`
- `org.eclipse.edc.connector.controlplane.asset.spi.index.DataAddressResolver`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.connector.controlplane.store.sql.assetindex.schema.AssetStatements` (optional)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper` (required)

Module `org.eclipse.edc:auth-basic:0.9.0`
-----------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.api.auth.basic.BasicAuthenticationExtension`
**Name:** "Basic authentication"

**Overview:**  Extension that registers an AuthenticationService that uses API Keys

 @deprecated this module is not supported anymore and it will be removed in the next iterations.



##### Configuration: 

| Key                             | Required | Type  | Default | Pattern | Min | Max | Description                                                              |
| ------------------------------- | -------- | ----- | ------- | ------- | --- | --- | ------------------------------------------------------------------------ |
| `edc.api.auth.basic.vault-keys` | `*`      | `map` | ``      |         |     |     | Key-value object defining authentication credentials stored in the vault |

##### Provided services:
- `org.eclipse.edc.api.auth.spi.AuthenticationService`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.security.Vault` (required)
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationRegistry` (required)

Module `org.eclipse.edc:auth-configuration:0.9.0`
-------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.api.auth.configuration.ApiAuthenticationConfigurationExtension`
**Name:** "Api Authentication Configuration Extension"

**Overview:** No overview provided.


##### Configuration: 

| Key                               | Required | Type     | Default | Pattern | Min | Max | Description                                                                     |
| --------------------------------- | -------- | -------- | ------- | ------- | --- | --- | ------------------------------------------------------------------------------- |
| `web.http.<context>.auth.type`    | `*`      | `string` | ``      |         |     |     | The type of the authentication provider.                                        |
| `web.http.<context>.auth.context` |          | `string` | ``      |         |     |     | The api context where to apply the authentication. Default to the web <context> |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationProviderRegistry` (required)
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationRegistry` (required)
- `org.eclipse.edc.web.spi.WebService` (required)

Module `org.eclipse.edc:auth-delegated:0.9.0`
---------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.api.auth.delegated.DelegatedAuthenticationExtension`
**Name:** "Delegating Authentication Service Extension"

**Overview:**  Extension that registers an AuthenticationService that delegates authentication and authorization to a third-party IdP
 and register an {@link ApiAuthenticationProvider} under the type called delegated



##### Configuration: 

| Key                                          | Required | Type     | Default  | Pattern | Min | Max | Description                                                                                |
| -------------------------------------------- | -------- | -------- | -------- | ------- | --- | --- | ------------------------------------------------------------------------------------------ |
| ~~edc.api.auth.dac.cache.validity~~          |          | `Long`   | `300000` |         |     |     | Duration (in ms) that the internal key cache is valid                                      |
| ~~edc.api.auth.dac.key.url~~                 |          | `string` | ``       |         |     |     | URL where the third-party IdP's public key(s) can be resolved                              |
| `web.http.<context>.auth.dac.key.url`        |          | `string` | ``       |         |     |     | URL where the third-party IdP's public key(s) can be resolved for the configured <context> |
| `web.http.<context>.auth.dac.cache.validity` |          | `Long`   | `300000` |         |     |     | Duration (in ms) that the internal key cache is valid for the configured <context>         |
| `edc.api.auth.dac.validation.tolerance`      |          | `string` | `5000`   |         |     |     | Default token validation time tolerance (in ms), e.g. for nbf or exp claims                |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationRegistry` (required)
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationProviderRegistry` (required)
- `org.eclipse.edc.token.spi.TokenValidationRulesRegistry` (required)
- `org.eclipse.edc.keys.spi.KeyParserRegistry` (required)
- `org.eclipse.edc.token.spi.TokenValidationService` (required)
- `java.time.Clock` (required)

Module `Auth services:0.9.0`
----------------------------
_org.eclipse.edc:auth-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationProviderRegistry`
  - `org.eclipse.edc.api.auth.spi.AuthenticationService`
  - `org.eclipse.edc.api.auth.spi.ApiAuthenticationProvider`

### Extensions
Module `org.eclipse.edc:auth-tokenbased:0.9.0`
----------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.api.auth.token.TokenBasedAuthenticationExtension`
**Name:** "Static token API Authentication"

**Overview:**  Extension that registers an AuthenticationService that uses API Keys and register
 an {@link ApiAuthenticationProvider} under the type called tokenbased



##### Configuration: 

| Key                                 | Required | Type     | Default | Pattern | Min | Max | Description                                      |
| ----------------------------------- | -------- | -------- | ------- | ------- | --- | --- | ------------------------------------------------ |
| `web.http.<context>.auth.key`       |          | `string` | ``      |         |     |     | The api key to use for the <context>             |
| `web.http.<context>.auth.key.alias` |          | `string` | ``      |         |     |     | The vault api key alias to use for the <context> |
| ~~edc.api.auth.key~~                |          | `string` | ``      |         |     |     |                                                  |
| ~~edc.api.auth.key.alias~~          |          | `string` | ``      |         |     |     |                                                  |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.spi.security.Vault` (required)
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationRegistry` (required)
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationProviderRegistry` (required)

Module `org.eclipse.edc:boot:0.9.0`
-----------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.boot.BootServicesExtension`
**Name:** "Boot Services"

**Overview:** No overview provided.


##### Configuration: 

| Key                  | Required | Type     | Default         | Pattern | Min | Max | Description                                                                                                                                                |
| -------------------- | -------- | -------- | --------------- | ------- | --- | --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `edc.participant.id` |          | `string` | ``              |         |     |     | Configures the participant id this runtime is operating on behalf of                                                                                       |
| `edc.runtime.id`     |          | `string` | `<random UUID>` |         |     |     | Configures the runtime id. This should be fully or partly randomized, and need not be stable across restarts. It is recommended to leave this value blank. |
| `edc.component.id`   |          | `string` | `<random UUID>` |         |     |     | Configures this component's ID. This should be a unique, stable and deterministic identifier.                                                              |

##### Provided services:
- `java.time.Clock`
- `org.eclipse.edc.spi.telemetry.Telemetry`
- `org.eclipse.edc.spi.system.health.HealthCheckService`
- `org.eclipse.edc.spi.security.Vault`
- `org.eclipse.edc.spi.system.ExecutorInstrumentation`
- `org.eclipse.edc.spi.system.apiversion.ApiVersionService`

##### Referenced (injected) services:
_None_

Module `org.eclipse.edc:callback-event-dispatcher:0.9.0`
--------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.callback.dispatcher.CallbackEventDispatcherExtension`
**Name:** "Callback dispatcher extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.controlplane.services.spi.callback.CallbackProtocolResolverRegistry`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.message.RemoteMessageDispatcherRegistry` (required)
- `org.eclipse.edc.spi.event.EventRouter` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.callback.CallbackRegistry` (required)

Module `org.eclipse.edc:callback-http-dispatcher:0.9.0`
-------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.callback.dispatcher.http.CallbackEventDispatcherHttpExtension`
**Name:** "Callback dispatcher http extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.spi.message.RemoteMessageDispatcherRegistry` (required)
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.callback.CallbackProtocolResolverRegistry` (required)
- `org.eclipse.edc.spi.security.Vault` (required)

Module `org.eclipse.edc:callback-static-endpoint:0.9.0`
-------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.callback.staticendpoint.CallbackStaticEndpointExtension`
**Name:** "Static callbacks extension"

**Overview:**  Extension for configuring the static endpoints for callbacks



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.services.spi.callback.CallbackRegistry` (required)

Module `org.eclipse.edc:catalog-api:0.9.0`
------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.api.management.catalog.CatalogApiExtension`
**Name:** "Management API: Catalog"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.catalog.CatalogService` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry` (required)

Module `org.eclipse.edc:configuration-filesystem:0.9.0`
-------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.configuration.filesystem.FsConfigurationExtension`
**Name:** "FS Configuration"

**Overview:**  Sources configuration values from a properties file.



##### Configuration: 

| Key             | Required | Type     | Default | Pattern | Min | Max | Description |
| --------------- | -------- | -------- | ------- | ------- | --- | --- | ----------- |
| `edc.fs.config` |          | `string` | ``      |         |     |     |             |

##### Provided services:
_None_

##### Referenced (injected) services:
_None_

Module `org.eclipse.edc:connector-core:0.9.0`
---------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.core.CoreServicesExtension`
**Name:** "Core Services"

**Overview:** No overview provided.


##### Configuration: 

| Key                      | Required | Type     | Default     | Pattern | Min | Max | Description                                                          |
| ------------------------ | -------- | -------- | ----------- | ------- | --- | --- | -------------------------------------------------------------------- |
| `edc.hostname`           |          | `string` | `localhost` |         |     |     | Connector hostname, which e.g. is used in referer urls               |
| `edc.agent.identity.key` |          | `string` | `client_id` |         |     |     | The name of the claim key used to determine the participant identity |

##### Provided services:
- `org.eclipse.edc.spi.types.TypeManager`
- `org.eclipse.edc.spi.system.Hostname`
- `org.eclipse.edc.spi.message.RemoteMessageDispatcherRegistry`
- `org.eclipse.edc.spi.command.CommandHandlerRegistry`
- `org.eclipse.edc.spi.agent.ParticipantAgentService`
- `org.eclipse.edc.policy.engine.spi.RuleBindingRegistry`
- `org.eclipse.edc.policy.engine.spi.PolicyEngine`
- `org.eclipse.edc.spi.event.EventRouter`
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry`
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry`
- `org.eclipse.edc.validator.spi.DataAddressValidatorRegistry`
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry`
- `org.eclipse.edc.http.spi.ControlApiHttpClient`

##### Referenced (injected) services:
- `org.eclipse.edc.connector.core.event.EventExecutorServiceContainer` (required)
- `org.eclipse.edc.spi.types.TypeManager` (optional)
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.api.auth.spi.ControlClientAuthenticationProvider` (required)

#### Class: `org.eclipse.edc.connector.core.LocalPublicKeyDefaultExtension`
**Name:** "Security Default Services Extension"

**Overview:** No overview provided.


##### Configuration: 

| Key                                  | Required | Type     | Default | Pattern | Min | Max | Description                                                                                                                                      |
| ------------------------------------ | -------- | -------- | ------- | ------- | --- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `edc.iam.publickeys.<pkAlias>.id`    | `*`      | `string` | ``      |         |     |     | ID of the public key.                                                                                                                            |
| `edc.iam.publickeys.<pkAlias>.value` |          | `string` | ``      |         |     |     | Value of the public key. Multiple formats are supported, depending on the KeyParsers registered in the runtime                                   |
| `edc.iam.publickeys.<pkAlias>.path`  |          | `string` | ``      |         |     |     | Path to a file that holds the public key, e.g. a PEM file. Multiple formats are supported, depending on the KeyParsers registered in the runtime |

##### Provided services:
- `org.eclipse.edc.keys.spi.LocalPublicKeyService`

##### Referenced (injected) services:
- `org.eclipse.edc.keys.spi.KeyParserRegistry` (required)
- `org.eclipse.edc.spi.security.Vault` (required)

#### Class: `org.eclipse.edc.connector.core.CoreDefaultServicesExtension`
**Name:** "CoreDefaultServicesExtension"

**Overview:** No overview provided.


##### Configuration: 

| Key                                      | Required | Type      | Default | Pattern | Min | Max | Description                                                         |
| ---------------------------------------- | -------- | --------- | ------- | ------- | --- | --- | ------------------------------------------------------------------- |
| `edc.core.retry.retries.max`             |          | `int`     | `5`     |         |     |     | RetryPolicy: Maximum retries before a failure is propagated         |
| `edc.core.retry.backoff.min`             |          | `int`     | `500`   |         |     |     | RetryPolicy: Minimum number of milliseconds for exponential backoff |
| `edc.core.retry.backoff.max`             |          | `int`     | `10000` |         |     |     | RetryPolicy: Maximum number of milliseconds for exponential backoff |
| `edc.core.retry.log.on.retry`            |          | `boolean` | `false` |         |     |     | RetryPolicy: Log onRetry events                                     |
| `edc.core.retry.log.on.retry.scheduled`  |          | `boolean` | `false` |         |     |     | RetryPolicy: Log onRetryScheduled events                            |
| `edc.core.retry.log.on.retries.exceeded` |          | `boolean` | `false` |         |     |     | RetryPolicy: Log onRetriesExceeded events                           |
| `edc.core.retry.log.on.failed.attempt`   |          | `boolean` | `false` |         |     |     | RetryPolicy: Log onFailedAttempt events                             |
| `edc.core.retry.log.on.abort`            |          | `boolean` | `false` |         |     |     | RetryPolicy: Log onAbort events                                     |
| `edc.http.client.https.enforce`          |          | `boolean` | `false` |         |     |     | OkHttpClient: If true, enable HTTPS call enforcement                |
| `edc.http.client.timeout.connect`        |          | `int`     | `30`    |         |     |     | OkHttpClient: connect timeout, in seconds                           |
| `edc.http.client.timeout.read`           |          | `int`     | `30`    |         |     |     | OkHttpClient: read timeout, in seconds                              |
| `edc.http.client.send.buffer.size`       |          | `int`     | `0`     |         |     |     | OkHttpClient: send buffer size, in bytes                            |
| `edc.http.client.receive.buffer.size`    |          | `int`     | `0`     |         |     |     | OkHttpClient: receive buffer size, in bytes                         |

##### Provided services:
- `org.eclipse.edc.transaction.spi.TransactionContext`
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry`
- `org.eclipse.edc.connector.core.event.EventExecutorServiceContainer`
- `org.eclipse.edc.http.spi.EdcHttpClient`
- `org.eclipse.edc.api.auth.spi.ControlClientAuthenticationProvider`
- `okhttp3.OkHttpClient`
- `dev.failsafe.RetryPolicy<T>`
- `org.eclipse.edc.spi.agent.ParticipantIdMapper`

##### Referenced (injected) services:
- `okhttp3.EventListener` (optional)

#### Class: `org.eclipse.edc.connector.core.SecurityDefaultServicesExtension`
**Name:** "Security Default Services Extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.keys.spi.PrivateKeyResolver`
- `org.eclipse.edc.keys.spi.CertificateResolver`
- `org.eclipse.edc.keys.spi.KeyParserRegistry`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.security.Vault` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:contract-agreement-api:0.9.0`
-----------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.api.management.contractagreement.ContractAgreementApiExtension`
**Name:** "Management API: Contract Agreement"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.contractagreement.ContractAgreementService` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)

Module `org.eclipse.edc:contract-definition-api:0.9.0`
------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.api.management.contractdefinition.ContractDefinitionApiExtension`
**Name:** "Management API: Contract Definition"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.contractdefinition.ContractDefinitionService` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry` (required)

Module `org.eclipse.edc:contract-definition-store-sql:0.9.0`
------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.store.sql.contractdefinition.SqlContractDefinitionStoreExtension`
**Name:** "SQL contract definition store"

**Overview:** No overview provided.


##### Configuration: 

| Key                                           | Required | Type     | Default   | Pattern | Min | Max | Description               |
| --------------------------------------------- | -------- | -------- | --------- | ------- | --- | --- | ------------------------- |
| `edc.sql.store.contractdefinition.datasource` |          | `string` | `default` |         |     |     | The datasource to be used |

##### Provided services:
- `org.eclipse.edc.connector.controlplane.contract.spi.offer.store.ContractDefinitionStore`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.connector.controlplane.store.sql.contractdefinition.schema.ContractDefinitionStatements` (optional)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper` (required)

Module `org.eclipse.edc:contract-negotiation-api:0.9.0`
-------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.api.management.contractnegotiation.ContractNegotiationApiExtension`
**Name:** "Management API: Contract Negotiation"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.contractnegotiation.ContractNegotiationService` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)

Module `org.eclipse.edc:contract-negotiation-store-sql:0.9.0`
-------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.store.sql.contractnegotiation.SqlContractNegotiationStoreExtension`
**Name:** "SQL contract negotiation store"

**Overview:** No overview provided.


##### Configuration: 

| Key                                            | Required | Type     | Default   | Pattern | Min | Max | Description               |
| ---------------------------------------------- | -------- | -------- | --------- | ------- | --- | --- | ------------------------- |
| `edc.sql.store.contractnegotiation.datasource` |          | `string` | `default` |         |     |     | The datasource to be used |

##### Provided services:
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.store.ContractNegotiationStore`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `java.time.Clock` (required)
- `org.eclipse.edc.connector.controlplane.store.sql.contractnegotiation.store.schema.ContractNegotiationStatements` (optional)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper` (required)

Module `Contract services:0.9.0`
--------------------------------
_org.eclipse.edc:contract-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.NegotiationWaitStrategy`
  - `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.observe.ContractNegotiationObservable`
  - `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.ProviderContractNegotiationManager`
  - `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.ConsumerContractNegotiationManager`
  - `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.ContractNegotiationPendingGuard`
  - `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.store.ContractNegotiationStore`
  - `org.eclipse.edc.connector.controlplane.contract.spi.validation.ContractValidationService`
  - `org.eclipse.edc.connector.controlplane.contract.spi.offer.ContractDefinitionResolver`
  - `org.eclipse.edc.connector.controlplane.contract.spi.offer.store.ContractDefinitionStore`

### Extensions
Module `org.eclipse.edc:control-api-configuration:0.9.0`
--------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.api.control.configuration.ControlApiConfigurationExtension`
**Name:** "Control API configuration"

**Overview:**  Tells all the Control API controllers under which context alias they need to register their resources: either
 `default` or `control`



##### Configuration: 

| Key                    | Required | Type     | Default | Pattern | Min | Max | Description                                                                                                  |
| ---------------------- | -------- | -------- | ------- | ------- | --- | --- | ------------------------------------------------------------------------------------------------------------ |
| `edc.control.endpoint` |          | `string` | ``      |         |     |     | Configures endpoint for reaching the Control API. If it's missing it defaults to the hostname configuration. |

##### Provided services:
- `org.eclipse.edc.web.spi.configuration.context.ControlApiUrl`

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebServer` (required)
- `org.eclipse.edc.web.spi.configuration.WebServiceConfigurer` (required)
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.spi.system.Hostname` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationRegistry` (required)
- `org.eclipse.edc.spi.system.apiversion.ApiVersionService` (required)

Module `org.eclipse.edc:control-plane-aggregate-services:0.9.0`
---------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.services.ControlPlaneServicesExtension`
**Name:** "Control Plane Services"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.controlplane.services.spi.asset.AssetService`
- `org.eclipse.edc.connector.spi.service.SecretService`
- `org.eclipse.edc.connector.controlplane.services.spi.catalog.CatalogService`
- `org.eclipse.edc.connector.controlplane.services.spi.catalog.CatalogProtocolService`
- `org.eclipse.edc.connector.controlplane.services.spi.contractagreement.ContractAgreementService`
- `org.eclipse.edc.connector.controlplane.services.spi.contractdefinition.ContractDefinitionService`
- `org.eclipse.edc.connector.controlplane.services.spi.contractnegotiation.ContractNegotiationService`
- `org.eclipse.edc.connector.controlplane.services.spi.contractnegotiation.ContractNegotiationProtocolService`
- `org.eclipse.edc.connector.controlplane.services.spi.policydefinition.PolicyDefinitionService`
- `org.eclipse.edc.connector.controlplane.services.spi.transferprocess.TransferProcessService`
- `org.eclipse.edc.connector.controlplane.services.spi.transferprocess.TransferProcessProtocolService`
- `org.eclipse.edc.connector.controlplane.services.spi.protocol.ProtocolTokenValidator`
- `org.eclipse.edc.connector.controlplane.services.spi.protocol.VersionProtocolService`

##### Referenced (injected) services:
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)
- `org.eclipse.edc.spi.event.EventRouter` (required)
- `org.eclipse.edc.spi.message.RemoteMessageDispatcherRegistry` (required)
- `org.eclipse.edc.connector.controlplane.asset.spi.index.AssetIndex` (required)
- `org.eclipse.edc.spi.security.Vault` (required)
- `org.eclipse.edc.connector.controlplane.contract.spi.offer.store.ContractDefinitionStore` (required)
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.store.ContractNegotiationStore` (required)
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.ConsumerContractNegotiationManager` (required)
- `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyDefinitionStore` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.store.TransferProcessStore` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.TransferProcessManager` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.connector.controlplane.contract.spi.validation.ContractValidationService` (required)
- `org.eclipse.edc.connector.controlplane.contract.spi.offer.ConsumerOfferResolver` (required)
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.observe.ContractNegotiationObservable` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.observe.TransferProcessObservable` (required)
- `org.eclipse.edc.spi.telemetry.Telemetry` (required)
- `org.eclipse.edc.spi.agent.ParticipantAgentService` (required)
- `org.eclipse.edc.connector.controlplane.catalog.spi.DataServiceRegistry` (required)
- `org.eclipse.edc.connector.controlplane.catalog.spi.DatasetResolver` (required)
- `org.eclipse.edc.spi.command.CommandHandlerRegistry` (required)
- `org.eclipse.edc.validator.spi.DataAddressValidatorRegistry` (required)
- `org.eclipse.edc.spi.iam.IdentityService` (required)
- `org.eclipse.edc.policy.engine.spi.PolicyEngine` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.protocol.ProtocolTokenValidator` (optional)
- `org.eclipse.edc.connector.controlplane.services.spi.protocol.ProtocolVersionRegistry` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.flow.DataFlowManager` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.flow.TransferTypeParser` (required)

Module `org.eclipse.edc:control-plane-api:0.9.0`
------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.api.ControlPlaneApiExtension`
**Name:** "Control Plane API"

**Overview:**  {@link ControlPlaneApiExtension } exposes HTTP endpoints for internal interaction with the Control Plane



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.transferprocess.TransferProcessService` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:control-plane-api-client:0.9.0`
-------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.api.client.ControlPlaneApiClientExtension`
**Name:** "Control Plane HTTP API client"

**Overview:**  Extensions that contains clients for Control Plane HTTP APIs



##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.controlplane.api.client.spi.transferprocess.TransferProcessApiClient`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.http.spi.ControlApiHttpClient` (required)

Module `Control Plane API Services:0.9.0`
-----------------------------------------
_org.eclipse.edc:control-plane-api-client-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.connector.controlplane.api.client.spi.transferprocess.TransferProcessApiClient`

### Extensions
Module `org.eclipse.edc:control-plane-catalog:0.9.0`
----------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.catalog.CatalogCoreExtension`
**Name:** "Catalog Core"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.controlplane.catalog.spi.DatasetResolver`

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.contract.spi.offer.ContractDefinitionResolver` (required)
- `org.eclipse.edc.connector.controlplane.asset.spi.index.AssetIndex` (required)
- `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyDefinitionStore` (required)
- `org.eclipse.edc.connector.controlplane.catalog.spi.DistributionResolver` (required)
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry` (required)

#### Class: `org.eclipse.edc.connector.controlplane.catalog.CatalogDefaultServicesExtension`
**Name:** "Catalog Default Services"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.controlplane.catalog.spi.DataServiceRegistry`
- `org.eclipse.edc.connector.controlplane.catalog.spi.DistributionResolver`

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.transfer.spi.flow.DataFlowManager` (required)

Module `org.eclipse.edc:control-plane-contract:0.9.0`
-----------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.contract.ContractCoreExtension`
**Name:** "Contract Core"

**Overview:** No overview provided.


##### Configuration: 

| Key                                                   | Required | Type   | Default | Pattern | Min | Max | Description                                                                                              |
| ----------------------------------------------------- | -------- | ------ | ------- | ------- | --- | --- | -------------------------------------------------------------------------------------------------------- |
| `edc.negotiation.state-machine.iteration-wait-millis` |          | `long` | ``      |         |     |     | the iteration wait time in milliseconds in the negotiation state machine. Default value 1000             |
| `edc.negotiation.consumer.state-machine.batch-size`   |          | `int`  | ``      |         |     |     | the batch size in the consumer negotiation state machine. Default value 20                               |
| `edc.negotiation.provider.state-machine.batch-size`   |          | `int`  | ``      |         |     |     | the batch size in the provider negotiation state machine. Default value 20                               |
| `edc.negotiation.consumer.send.retry.limit`           |          | `int`  | `7`     |         |     |     | how many times a specific operation must be tried before terminating the consumer negotiation with error |
| `edc.negotiation.provider.send.retry.limit`           |          | `int`  | `7`     |         |     |     | how many times a specific operation must be tried before terminating the provider negotiation with error |
| `edc.negotiation.consumer.send.retry.base-delay.ms`   |          | `long` | `1000`  |         |     |     | The base delay for the consumer negotiation retry mechanism in millisecond                               |
| `edc.negotiation.provider.send.retry.base-delay.ms`   |          | `long` | `1000`  |         |     |     | The base delay for the provider negotiation retry mechanism in millisecond                               |

##### Provided services:
- `org.eclipse.edc.connector.controlplane.contract.spi.validation.ContractValidationService`
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.ConsumerContractNegotiationManager`
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.ProviderContractNegotiationManager`

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.asset.spi.index.AssetIndex` (required)
- `org.eclipse.edc.spi.message.RemoteMessageDispatcherRegistry` (required)
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.store.ContractNegotiationStore` (required)
- `org.eclipse.edc.policy.engine.spi.PolicyEngine` (required)
- `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyDefinitionStore` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)
- `org.eclipse.edc.spi.telemetry.Telemetry` (required)
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.event.EventRouter` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.policy.engine.spi.RuleBindingRegistry` (required)
- `org.eclipse.edc.spi.protocol.ProtocolWebhook` (required)
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.observe.ContractNegotiationObservable` (required)
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.ContractNegotiationPendingGuard` (required)
- `org.eclipse.edc.spi.system.ExecutorInstrumentation` (required)

#### Class: `org.eclipse.edc.connector.controlplane.contract.ContractNegotiationCommandExtension`
**Name:** "Contract Negotiation command handlers"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.store.ContractNegotiationStore` (required)
- `org.eclipse.edc.spi.command.CommandHandlerRegistry` (required)

#### Class: `org.eclipse.edc.connector.controlplane.contract.ContractNegotiationDefaultServicesExtension`
**Name:** "Contract Negotiation Default Services"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.controlplane.contract.spi.offer.ContractDefinitionResolver`
- `org.eclipse.edc.connector.controlplane.contract.spi.offer.ConsumerOfferResolver`
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.observe.ContractNegotiationObservable`
- `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyArchive`
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.ContractNegotiationPendingGuard`

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.contract.spi.offer.store.ContractDefinitionStore` (required)
- `org.eclipse.edc.policy.engine.spi.PolicyEngine` (required)
- `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyDefinitionStore` (required)
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.store.ContractNegotiationStore` (required)

Module `org.eclipse.edc:control-plane-core:0.9.0`
-------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.ControlPlaneDefaultServicesExtension`
**Name:** "Control Plane Default Services"

**Overview:**  Provides default service implementations for fallback



##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.controlplane.asset.spi.index.AssetIndex`
- `org.eclipse.edc.connector.controlplane.asset.spi.index.DataAddressResolver`
- `org.eclipse.edc.connector.controlplane.contract.spi.offer.store.ContractDefinitionStore`
- `org.eclipse.edc.connector.controlplane.contract.spi.negotiation.store.ContractNegotiationStore`
- `org.eclipse.edc.connector.controlplane.transfer.spi.store.TransferProcessStore`
- `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyDefinitionStore`
- `org.eclipse.edc.connector.controlplane.services.spi.callback.CallbackRegistry`
- `org.eclipse.edc.connector.controlplane.services.spi.protocol.ProtocolVersionRegistry`

##### Referenced (injected) services:
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry` (required)

Module `org.eclipse.edc:control-plane-transfer:0.9.0`
-----------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.transfer.TransferCoreExtension`
**Name:** "Transfer Core"

**Overview:** No overview provided.


##### Configuration: 

| Key                                                | Required | Type   | Default | Pattern | Min | Max | Description                                                                                       |
| -------------------------------------------------- | -------- | ------ | ------- | ------- | --- | --- | ------------------------------------------------------------------------------------------------- |
| `edc.transfer.state-machine.iteration-wait-millis` |          | `long` | ``      |         |     |     | the iteration wait time in milliseconds in the transfer process state machine. Default value 1000 |
| `edc.transfer.state-machine.batch-size`            |          | `int`  | ``      |         |     |     | the batch size in the transfer process state machine. Default value 20                            |
| `edc.transfer.send.retry.limit`                    |          | `int`  | `7`     |         |     |     | how many times a specific operation must be tried before terminating the transfer with error      |
| `edc.transfer.send.retry.base-delay.ms`            |          | `long` | `1000`  |         |     |     | The base delay for the transfer retry mechanism in millisecond                                    |

##### Provided services:
- `org.eclipse.edc.connector.controlplane.transfer.spi.TransferProcessManager`
- `org.eclipse.edc.connector.controlplane.transfer.spi.edr.EndpointDataReferenceReceiverRegistry`

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.transfer.spi.store.TransferProcessStore` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.flow.DataFlowManager` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.provision.ResourceManifestGenerator` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.provision.ProvisionManager` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.observe.TransferProcessObservable` (required)
- `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyArchive` (required)
- `org.eclipse.edc.spi.command.CommandHandlerRegistry` (required)
- `org.eclipse.edc.spi.message.RemoteMessageDispatcherRegistry` (required)
- `org.eclipse.edc.connector.controlplane.asset.spi.index.DataAddressResolver` (required)
- `org.eclipse.edc.spi.security.Vault` (required)
- `org.eclipse.edc.spi.event.EventRouter` (required)
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.spi.telemetry.Telemetry` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.spi.protocol.ProtocolWebhook` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.TransferProcessPendingGuard` (required)
- `org.eclipse.edc.spi.system.ExecutorInstrumentation` (required)

#### Class: `org.eclipse.edc.connector.controlplane.transfer.TransferProcessDefaultServicesExtension`
**Name:** "Transfer Process Default Services"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.controlplane.transfer.spi.flow.DataFlowManager`
- `org.eclipse.edc.connector.controlplane.transfer.spi.provision.ResourceManifestGenerator`
- `org.eclipse.edc.connector.controlplane.transfer.spi.provision.ProvisionManager`
- `org.eclipse.edc.connector.controlplane.transfer.spi.observe.TransferProcessObservable`
- `org.eclipse.edc.connector.controlplane.transfer.spi.TransferProcessPendingGuard`
- `org.eclipse.edc.connector.controlplane.transfer.spi.flow.TransferTypeParser`

##### Referenced (injected) services:
- `org.eclipse.edc.policy.engine.spi.PolicyEngine` (required)

#### Class: `org.eclipse.edc.connector.controlplane.transfer.TransferProcessCommandExtension`
**Name:** "TransferProcessCommandExtension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.transfer.spi.store.TransferProcessStore` (required)

Module `Core services:0.9.0`
----------------------------
_org.eclipse.edc:core-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.spi.agent.ParticipantIdMapper`
  - `org.eclipse.edc.spi.command.CommandHandlerRegistry`
  - `org.eclipse.edc.spi.iam.AudienceResolver`
  - `org.eclipse.edc.spi.iam.IdentityService`
  - `org.eclipse.edc.spi.message.RemoteMessageDispatcherRegistry`
  - `org.eclipse.edc.spi.event.EventRouter`

### Extensions
Module `org.eclipse.edc:data-plane-core:0.9.0`
----------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.framework.DataPlaneDefaultServicesExtension`
**Name:** "Data Plane Framework Default Services"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.dataplane.framework.registry.TransferServiceSelectionStrategy`
- `org.eclipse.edc.connector.dataplane.spi.store.DataPlaneStore`
- `org.eclipse.edc.connector.dataplane.spi.store.AccessTokenDataStore`
- `org.eclipse.edc.connector.dataplane.spi.pipeline.PipelineService`
- `org.eclipse.edc.connector.dataplane.spi.iam.PublicEndpointGeneratorService`
- `org.eclipse.edc.connector.dataplane.spi.iam.DataPlaneAuthorizationService`

##### Referenced (injected) services:
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry` (required)

#### Class: `org.eclipse.edc.connector.dataplane.framework.DataPlaneFrameworkExtension`
**Name:** "Data Plane Framework"

**Overview:** No overview provided.


##### Configuration: 

| Key                                                 | Required | Type   | Default | Pattern | Min | Max | Description                                                                                          |
| --------------------------------------------------- | -------- | ------ | ------- | ------- | --- | --- | ---------------------------------------------------------------------------------------------------- |
| `edc.dataplane.state-machine.iteration-wait-millis` |          | `long` | `1000`  |         |     |     | the iteration wait time in milliseconds in the data plane state machine.                             |
| `edc.dataplane.state-machine.batch-size`            |          | `int`  | `20`    |         |     |     | the batch size in the data plane state machine.                                                      |
| `edc.dataplane.send.retry.limit`                    |          | `int`  | `7`     |         |     |     | how many times a specific operation must be tried before terminating the dataplane with error        |
| `edc.dataplane.send.retry.base-delay.ms`            |          | `long` | `1000`  |         |     |     | The base delay for the dataplane retry mechanism in millisecond                                      |
| `edc.dataplane.transfer.threads`                    |          | `int`  | `20`    |         |     |     | Size of the transfer thread pool. It is advisable to set it bigger than the state machine batch size |

##### Provided services:
- `org.eclipse.edc.connector.dataplane.spi.manager.DataPlaneManager`
- `org.eclipse.edc.connector.dataplane.spi.registry.TransferServiceRegistry`
- `org.eclipse.edc.connector.dataplane.spi.pipeline.DataTransferExecutorServiceContainer`

##### Referenced (injected) services:
- `org.eclipse.edc.connector.dataplane.framework.registry.TransferServiceSelectionStrategy` (required)
- `org.eclipse.edc.connector.dataplane.spi.store.DataPlaneStore` (required)
- `org.eclipse.edc.connector.controlplane.api.client.spi.transferprocess.TransferProcessApiClient` (required)
- `org.eclipse.edc.spi.system.ExecutorInstrumentation` (required)
- `org.eclipse.edc.spi.telemetry.Telemetry` (required)
- `java.time.Clock` (required)
- `org.eclipse.edc.connector.dataplane.spi.pipeline.PipelineService` (required)
- `org.eclipse.edc.connector.dataplane.spi.iam.DataPlaneAuthorizationService` (required)

Module `org.eclipse.edc:data-plane-http:0.9.0`
----------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.http.DataPlaneHttpExtension`
**Name:** "Data Plane HTTP"

**Overview:**  Provides support for reading data from an HTTP endpoint and sending data to an HTTP endpoint.



##### Configuration: 

| Key                                      | Required | Type  | Default | Pattern | Min | Max | Description                                                        |
| ---------------------------------------- | -------- | ----- | ------- | ------- | --- | --- | ------------------------------------------------------------------ |
| `edc.dataplane.http.sink.partition.size` |          | `int` | `5`     |         |     |     | Number of partitions for parallel message push in the HttpDataSink |

##### Provided services:
- `org.eclipse.edc.connector.dataplane.http.spi.HttpRequestParamsProvider`

##### Referenced (injected) services:
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.connector.dataplane.spi.pipeline.PipelineService` (required)
- `org.eclipse.edc.connector.dataplane.spi.pipeline.DataTransferExecutorServiceContainer` (required)
- `org.eclipse.edc.spi.security.Vault` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:data-plane-http-oauth2-core:0.9.0`
----------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.http.oauth2.DataPlaneHttpOauth2Extension`
**Name:** "Data Plane HTTP OAuth2"

**Overview:**  Provides support for adding OAuth2 authentication to http data transfer



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `java.time.Clock` (required)
- `org.eclipse.edc.connector.dataplane.http.spi.HttpRequestParamsProvider` (required)
- `org.eclipse.edc.spi.security.Vault` (required)
- `org.eclipse.edc.jwt.signer.spi.JwsSignerProvider` (required)
- `org.eclipse.edc.iam.oauth2.spi.client.Oauth2Client` (required)

Module `org.eclipse.edc:data-plane-iam:0.9.0`
---------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.iam.DataPlaneIamExtension`
**Name:** "Data Plane IAM"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.dataplane.spi.iam.DataPlaneAuthorizationService`

##### Referenced (injected) services:
- `java.time.Clock` (required)
- `org.eclipse.edc.connector.dataplane.spi.iam.DataPlaneAccessTokenService` (required)
- `org.eclipse.edc.connector.dataplane.spi.iam.DataPlaneAccessControlService` (required)
- `org.eclipse.edc.connector.dataplane.spi.iam.PublicEndpointGeneratorService` (required)

#### Class: `org.eclipse.edc.connector.dataplane.iam.DataPlaneIamDefaultServicesExtension`
**Name:** "Data Plane Default IAM Services"

**Overview:** No overview provided.


##### Configuration: 

| Key                                                 | Required | Type     | Default | Pattern | Min | Max | Description                                                                       |
| --------------------------------------------------- | -------- | -------- | ------- | ------- | --- | --- | --------------------------------------------------------------------------------- |
| `edc.transfer.proxy.token.signer.privatekey.alias`  |          | `string` | ``      |         |     |     | Alias of private key used for signing tokens, retrieved from private key resolver |
| `edc.transfer.proxy.token.verifier.publickey.alias` |          | `string` | ``      |         |     |     | Alias of public key used for verifying the tokens, retrieved from the vault       |

##### Provided services:
- `org.eclipse.edc.connector.dataplane.spi.iam.DataPlaneAccessControlService`
- `org.eclipse.edc.connector.dataplane.spi.iam.DataPlaneAccessTokenService`

##### Referenced (injected) services:
- `org.eclipse.edc.connector.dataplane.spi.store.AccessTokenDataStore` (required)
- `org.eclipse.edc.token.spi.TokenValidationService` (required)
- `org.eclipse.edc.keys.spi.LocalPublicKeyService` (required)
- `org.eclipse.edc.jwt.signer.spi.JwsSignerProvider` (required)

Module `org.eclipse.edc:data-plane-instance-store-sql:0.9.0`
------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.selector.store.sql.SqlDataPlaneInstanceStoreExtension`
**Name:** "Sql Data Plane Instance Store"

**Overview:**  Extensions that expose an implementation of {@link DataPlaneInstanceStore} that uses SQL as backend storage



##### Configuration: 

| Key                                          | Required | Type     | Default   | Pattern | Min | Max | Description                                                      |
| -------------------------------------------- | -------- | -------- | --------- | ------- | --- | --- | ---------------------------------------------------------------- |
| ~~edc.datasource.dataplaneinstance.name~~    |          | `string` | ``        |         |     |     | Name of the datasource to use for accessing data plane instances |
| `edc.sql.store.dataplaneinstance.datasource` |          | `string` | `default` |         |     |     | The datasource to be used                                        |

##### Provided services:
- `org.eclipse.edc.connector.dataplane.selector.spi.store.DataPlaneInstanceStore`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.connector.dataplane.selector.store.sql.schema.DataPlaneInstanceStatements` (optional)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `java.time.Clock` (required)
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper` (required)

Module `org.eclipse.edc:data-plane-kafka:0.9.0`
-----------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.kafka.DataPlaneKafkaExtension`
**Name:** "Data Plane Kafka"

**Overview:** No overview provided.


##### Configuration: 

| Key                                       | Required | Type  | Default | Pattern | Min | Max | Description                                   |
| ----------------------------------------- | -------- | ----- | ------- | ------- | --- | --- | --------------------------------------------- |
| `edc.dataplane.kafka.sink.partition.size` |          | `int` | `5`     |         |     |     | The partitionSize used by the kafka data sink |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.connector.dataplane.spi.pipeline.DataTransferExecutorServiceContainer` (required)
- `org.eclipse.edc.connector.dataplane.spi.pipeline.PipelineService` (required)
- `java.time.Clock` (required)

Module `org.eclipse.edc:data-plane-public-api-v2:0.9.0`
-------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.api.DataPlanePublicApiV2Extension`
**Name:** "Data Plane Public API"

**Overview:**  This extension provides generic endpoints which are open to public participants of the Dataspace to execute
 requests on the actual data source.



##### Configuration: 

| Key                                | Required | Type     | Default                            | Pattern | Min | Max | Description                                                                                                                                     |
| ---------------------------------- | -------- | -------- | ---------------------------------- | ------- | --- | --- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `edc.dataplane.api.public.baseurl` |          | `string` | `http://<HOST>:8185/api/v2/public` |         |     |     | Base url of the public API endpoint without the trailing slash. This should correspond to the values configured in '8185' and '/api/v2/public'. |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebServer` (required)
- `org.eclipse.edc.web.spi.configuration.WebServiceConfigurer` (required)
- `org.eclipse.edc.connector.dataplane.spi.pipeline.PipelineService` (required)
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.spi.system.ExecutorInstrumentation` (required)
- `org.eclipse.edc.connector.dataplane.spi.iam.DataPlaneAuthorizationService` (required)
- `org.eclipse.edc.connector.dataplane.spi.iam.PublicEndpointGeneratorService` (required)
- `org.eclipse.edc.spi.system.Hostname` (required)

Module `org.eclipse.edc:data-plane-selector-api:0.9.0`
------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.selector.DataPlaneSelectorApiExtension`
**Name:** "DataPlane selector API"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.connector.dataplane.selector.spi.DataPlaneSelectorService` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)
- `java.time.Clock` (required)

Module `org.eclipse.edc:data-plane-selector-client:0.9.0`
---------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.selector.DataPlaneSelectorClientExtension`
**Name:** "DataPlane Selector client"

**Overview:** No overview provided.


##### Configuration: 

| Key                                      | Required | Type     | Default  | Pattern | Min | Max | Description                                                                                              |
| ---------------------------------------- | -------- | -------- | -------- | ------- | --- | --- | -------------------------------------------------------------------------------------------------------- |
| `edc.dpf.selector.url`                   | `*`      | `string` | ``       |         |     |     | DataPlane selector api URL                                                                               |
| `edc.dataplane.client.selector.strategy` |          | `string` | `random` |         |     |     | Defines strategy for Data Plane instance selection in case Data Plane is not embedded in current runtime |

##### Provided services:
- `org.eclipse.edc.connector.dataplane.selector.spi.DataPlaneSelectorService`

##### Referenced (injected) services:
- `org.eclipse.edc.http.spi.ControlApiHttpClient` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)

Module `org.eclipse.edc:data-plane-selector-control-api:0.9.0`
--------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.selector.control.api.DataplaneSelectorControlApiExtension`
**Name:** "Dataplane Selector Control API"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.connector.dataplane.selector.spi.DataPlaneSelectorService` (required)
- `java.time.Clock` (required)

Module `org.eclipse.edc:data-plane-selector-core:0.9.0`
-------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.selector.DataPlaneSelectorExtension`
**Name:** "Data Plane Selector core"

**Overview:** No overview provided.


##### Configuration: 

| Key                                                           | Required | Type   | Default | Pattern | Min | Max | Description                                                                       |
| ------------------------------------------------------------- | -------- | ------ | ------- | ------- | --- | --- | --------------------------------------------------------------------------------- |
| `edc.data.plane.selector.state-machine.iteration-wait-millis` |          | `long` | `1000`  |         |     |     | the iteration wait time in milliseconds in the data plane selector state machine. |
| `edc.data.plane.selector.state-machine.batch-size`            |          | `int`  | `20`    |         |     |     | the batch size in the data plane selector state machine.                          |
| `edc.data.plane.selector.state-machine.check.period`          |          | `int`  | `60`    |         |     |     | the check period for data plane availability, in seconds                          |

##### Provided services:
- `org.eclipse.edc.connector.dataplane.selector.spi.DataPlaneSelectorService`

##### Referenced (injected) services:
- `org.eclipse.edc.connector.dataplane.selector.spi.store.DataPlaneInstanceStore` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.connector.dataplane.selector.spi.strategy.SelectionStrategyRegistry` (required)
- `org.eclipse.edc.connector.dataplane.selector.spi.client.DataPlaneClientFactory` (required)

#### Class: `org.eclipse.edc.connector.dataplane.selector.DataPlaneSelectorDefaultServicesExtension`
**Name:** "DataPlaneSelectorDefaultServicesExtension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.dataplane.selector.spi.store.DataPlaneInstanceStore`
- `org.eclipse.edc.connector.dataplane.selector.spi.strategy.SelectionStrategyRegistry`

##### Referenced (injected) services:
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry` (required)

Module `DataPlane selector services:0.9.0`
------------------------------------------
_org.eclipse.edc:data-plane-selector-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.connector.dataplane.selector.spi.client.DataPlaneClient`
  - `org.eclipse.edc.connector.dataplane.selector.spi.DataPlaneSelectorService`

### Extensions
Module `org.eclipse.edc:data-plane-self-registration:0.9.0`
-----------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.registration.DataplaneSelfRegistrationExtension`
**Name:** "Dataplane Self Registration"

**Overview:** No overview provided.


##### Configuration: 

| Key                                  | Required | Type      | Default | Pattern | Min | Max | Description                                                                              |
| ------------------------------------ | -------- | --------- | ------- | ------- | --- | --- | ---------------------------------------------------------------------------------------- |
| `edc.data.plane.self.unregistration` |          | `boolean` | `false` |         |     |     | Enable data-plane un-registration at shutdown (not suggested for clustered environments) |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.connector.dataplane.selector.spi.DataPlaneSelectorService` (required)
- `org.eclipse.edc.web.spi.configuration.context.ControlApiUrl` (required)
- `org.eclipse.edc.connector.dataplane.spi.pipeline.PipelineService` (required)
- `org.eclipse.edc.connector.dataplane.spi.iam.PublicEndpointGeneratorService` (required)
- `org.eclipse.edc.spi.system.health.HealthCheckService` (required)

Module `org.eclipse.edc:data-plane-signaling-api:0.9.0`
-------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.api.DataPlaneSignalingApiExtension`
**Name:** "DataPlane Signaling API extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.connector.dataplane.spi.manager.DataPlaneManager` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:data-plane-signaling-client:0.9.0`
----------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.client.DataPlaneSignalingClientTransformExtension`
**Name:** "Data Plane Signaling transform Client"

**Overview:**  This extension registers all the transformers relevant for the data plane signaling protocol



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

#### Class: `org.eclipse.edc.connector.dataplane.client.DataPlaneSignalingClientExtension`
**Name:** "Data Plane Signaling Client"

**Overview:**  This extension registers all the transformers relevant for the data plane signaling protocol



##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.dataplane.selector.spi.client.DataPlaneClientFactory`

##### Referenced (injected) services:
- `org.eclipse.edc.http.spi.ControlApiHttpClient` (optional)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)
- `org.eclipse.edc.connector.dataplane.spi.manager.DataPlaneManager` (optional)

Module `DataPlane services:0.9.0`
---------------------------------
_org.eclipse.edc:data-plane-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.connector.dataplane.spi.registry.TransferServiceRegistry`
  - `org.eclipse.edc.connector.dataplane.spi.iam.DataPlaneAccessTokenService`
  - `org.eclipse.edc.connector.dataplane.spi.iam.DataPlaneAccessControlService`
  - `org.eclipse.edc.connector.dataplane.spi.manager.DataPlaneManager`
  - `org.eclipse.edc.connector.dataplane.spi.pipeline.PipelineService`

### Extensions
Module `org.eclipse.edc:data-plane-store-sql:0.9.0`
---------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.dataplane.store.sql.SqlDataPlaneStoreExtension`
**Name:** "Sql Data Plane Store"

**Overview:**  Provides Sql Store for Data Plane Flow Requests states



##### Configuration: 

| Key                                  | Required | Type     | Default   | Pattern | Min | Max | Description                                                  |
| ------------------------------------ | -------- | -------- | --------- | ------- | --- | --- | ------------------------------------------------------------ |
| ~~edc.datasource.dataplane.name~~    |          | `string` | ``        |         |     |     | Name of the datasource to use for accessing data plane store |
| `edc.sql.store.dataplane.datasource` |          | `string` | `default` |         |     |     | The datasource to be used                                    |

##### Provided services:
- `org.eclipse.edc.connector.dataplane.spi.store.DataPlaneStore`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.connector.dataplane.store.sql.schema.DataPlaneStatements` (optional)
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper` (required)

Module `org.eclipse.edc:dsp-catalog-http-api:0.9.0`
---------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.catalog.http.api.DspCatalogApiExtension`
**Name:** "Dataspace Protocol Catalog Extension"

**Overview:**  Creates and registers the controller for dataspace protocol catalog requests.



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.spi.protocol.ProtocolWebhook` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.catalog.CatalogProtocolService` (required)
- `org.eclipse.edc.connector.controlplane.catalog.spi.DataServiceRegistry` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)
- `org.eclipse.edc.protocol.dsp.http.spi.message.DspRequestHandler` (required)
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.protocol.ProtocolVersionRegistry` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)

Module `org.eclipse.edc:dsp-catalog-http-dispatcher:0.9.0`
----------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.catalog.http.dispatcher.DspCatalogHttpDispatcherExtension`
**Name:** "Dataspace Protocol Catalog HTTP Dispatcher Extension"

**Overview:**  Creates and registers the HTTP dispatcher delegate for sending a catalog request as defined in
 the dataspace protocol specification.



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.protocol.dsp.http.spi.dispatcher.DspHttpRemoteMessageDispatcher` (required)
- `org.eclipse.edc.protocol.dsp.http.spi.serialization.JsonLdRemoteMessageSerializer` (required)

Module `org.eclipse.edc:dsp-catalog-transform:0.9.0`
----------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.catalog.transform.DspCatalogTransformExtension`
**Name:** "Dataspace Protocol Catalog Transform Extension"

**Overview:**  Provides the transformers for catalog message types via the {@link TypeTransformerRegistry}.



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.spi.agent.ParticipantIdMapper` (required)

Module `org.eclipse.edc:dsp-http-api-configuration:0.9.0`
---------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.http.api.configuration.DspApiConfigurationExtension`
**Name:** "Dataspace Protocol API Configuration Extension"

**Overview:**  Configure 'protocol' api context.



##### Configuration: 

| Key                        | Required | Type     | Default                                  | Pattern | Min | Max | Description                                        |
| -------------------------- | -------- | -------- | ---------------------------------------- | ------- | --- | --- | -------------------------------------------------- |
| `edc.dsp.callback.address` |          | `string` | `<hostname:protocol.port/protocol.path>` |         |     |     | Configures endpoint for reaching the Protocol API. |

##### Provided services:
- `org.eclipse.edc.spi.protocol.ProtocolWebhook`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.web.spi.WebServer` (required)
- `org.eclipse.edc.web.spi.configuration.WebServiceConfigurer` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.spi.agent.ParticipantIdMapper` (required)
- `org.eclipse.edc.spi.system.Hostname` (required)

Module `org.eclipse.edc:dsp-http-core:0.9.0`
--------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.http.DspHttpCoreExtension`
**Name:** "Dataspace Protocol Core Extension"

**Overview:**  Provides an implementation of {@link DspHttpRemoteMessageDispatcher} to support sending dataspace
 protocol messages. The dispatcher can then be used by other extensions to add support for
 specific message types.



##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.protocol.dsp.http.spi.dispatcher.DspHttpRemoteMessageDispatcher`
- `org.eclipse.edc.protocol.dsp.http.spi.message.DspRequestHandler`
- `org.eclipse.edc.protocol.dsp.http.spi.serialization.JsonLdRemoteMessageSerializer`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.message.RemoteMessageDispatcherRegistry` (required)
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.spi.iam.IdentityService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)
- `org.eclipse.edc.token.spi.TokenDecorator` (optional)
- `org.eclipse.edc.policy.engine.spi.PolicyEngine` (required)
- `org.eclipse.edc.spi.iam.AudienceResolver` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)

Module `org.eclipse.edc:dsp-negotiation-http-api:0.9.0`
-------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.negotiation.http.api.DspNegotiationApiExtension`
**Name:** "Dataspace Protocol Negotiation Api"

**Overview:**  Creates and registers the controller for dataspace protocol negotiation requests.



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.contractnegotiation.ContractNegotiationProtocolService` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)
- `org.eclipse.edc.protocol.dsp.http.spi.message.DspRequestHandler` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.protocol.ProtocolVersionRegistry` (required)

Module `org.eclipse.edc:dsp-negotiation-http-dispatcher:0.9.0`
--------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.negotiation.http.dispatcher.DspNegotiationHttpDispatcherExtension`
**Name:** "Dataspace Protocol Negotiation HTTP Dispatcher Extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.protocol.dsp.http.spi.dispatcher.DspHttpRemoteMessageDispatcher` (required)
- `org.eclipse.edc.protocol.dsp.http.spi.serialization.JsonLdRemoteMessageSerializer` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)

Module `org.eclipse.edc:dsp-negotiation-transform:0.9.0`
--------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.negotiation.transform.DspNegotiationTransformExtension`
**Name:** "Dataspace Protocol Negotiation Transform Extension"

**Overview:**  Provides the transformers for negotiation message types via the {@link TypeTransformerRegistry}.



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)

Module `org.eclipse.edc:dsp-transfer-process-http-api:0.9.0`
------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.transferprocess.http.api.DspTransferProcessApiExtension`
**Name:** "Dataspace Protocol: TransferProcess API Extension"

**Overview:**  Creates and registers the controller for dataspace protocol transfer process requests.



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.transferprocess.TransferProcessProtocolService` (required)
- `org.eclipse.edc.protocol.dsp.http.spi.message.DspRequestHandler` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.protocol.ProtocolVersionRegistry` (required)

Module `org.eclipse.edc:dsp-transfer-process-http-dispatcher:0.9.0`
-------------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.transferprocess.http.dispatcher.DspTransferProcessDispatcherExtension`
**Name:** "Dataspace Protocol Transfer HTTP Dispatcher Extension"

**Overview:**  Provides HTTP dispatching for Dataspace Protocol transfer process messages via the {@link DspHttpRemoteMessageDispatcher}.



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.protocol.dsp.http.spi.dispatcher.DspHttpRemoteMessageDispatcher` (required)
- `org.eclipse.edc.protocol.dsp.http.spi.serialization.JsonLdRemoteMessageSerializer` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)

Module `org.eclipse.edc:dsp-transfer-process-transform:0.9.0`
-------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.transferprocess.transform.DspTransferProcessTransformExtension`
**Name:** "Dataspace Protocol Transfer Process Transform Extension"

**Overview:**  Provides the transformers for transferprocess message types via the {@link TypeTransformerRegistry}.



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:dsp-version-http-api:0.9.0`
---------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.protocol.dsp.version.http.api.DspVersionApiExtension`
**Name:** "Dataspace Protocol Version Api"

**Overview:**  Provide API for the protocol versions.



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.protocol.dsp.http.spi.message.DspRequestHandler` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.protocol.VersionProtocolService` (required)

Module `org.eclipse.edc:edr-cache-api:0.9.0`
--------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.api.management.edr.EdrCacheApiExtension`
**Name:** "Management API: EDR cache"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)
- `org.eclipse.edc.edr.spi.store.EndpointDataReferenceStore` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)

Module `org.eclipse.edc:edr-index-sql:0.9.0`
--------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.edr.store.index.SqlEndpointDataReferenceEntryIndexExtension`
**Name:** "SQL edr entry store"

**Overview:** No overview provided.


##### Configuration: 

| Key                            | Required | Type     | Default   | Pattern | Min | Max | Description               |
| ------------------------------ | -------- | -------- | --------- | ------- | --- | --- | ------------------------- |
| `edc.sql.store.edr.datasource` |          | `string` | `default` |         |     |     | The datasource to be used |

##### Provided services:
- `org.eclipse.edc.edr.spi.store.EndpointDataReferenceEntryIndex`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.edr.store.index.sql.schema.EndpointDataReferenceEntryStatements` (optional)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper` (required)

Module `org.eclipse.edc:edr-store-core:0.9.0`
---------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.edr.store.EndpointDataReferenceStoreExtension`
**Name:** "Endpoint Data Reference Core Extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.edr.spi.store.EndpointDataReferenceStore`

##### Referenced (injected) services:
- `org.eclipse.edc.edr.spi.store.EndpointDataReferenceEntryIndex` (required)
- `org.eclipse.edc.edr.spi.store.EndpointDataReferenceCache` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)

#### Class: `org.eclipse.edc.edr.store.EndpointDataReferenceStoreDefaultServicesExtension`
**Name:** "Endpoint Data Reference Core Extension"

**Overview:** No overview provided.


##### Configuration: 

| Key                  | Required | Type     | Default | Pattern | Min | Max | Description                                                                                        |
| -------------------- | -------- | -------- | ------- | ------- | --- | --- | -------------------------------------------------------------------------------------------------- |
| `edc.edr.vault.path` |          | `string` | ``      |         |     |     | Directory/Path where to store EDRs in the vault for vaults that supports hierarchical structuring. |

##### Provided services:
- `org.eclipse.edc.edr.spi.store.EndpointDataReferenceCache`
- `org.eclipse.edc.edr.spi.store.EndpointDataReferenceEntryIndex`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry` (required)
- `org.eclipse.edc.spi.security.Vault` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:edr-store-receiver:0.9.0`
-------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.edr.store.receiver.EndpointDataReferenceStoreReceiverExtension`
**Name:** "Endpoint Data Reference Store Receiver Extension"

**Overview:** No overview provided.


##### Configuration: 

| Key                     | Required | Type     | Default | Pattern | Min | Max | Description                                                         |
| ----------------------- | -------- | -------- | ------- | ------- | --- | --- | ------------------------------------------------------------------- |
| `edc.edr.receiver.sync` |          | `string` | `false` |         |     |     | If true the EDR receiver will be registered as synchronous listener |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.spi.event.EventRouter` (required)
- `org.eclipse.edc.edr.spi.store.EndpointDataReferenceStore` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.contractagreement.ContractAgreementService` (required)
- `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyArchive` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)

Module `org.eclipse.edc:events-cloud-http:0.9.0`
------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.event.cloud.http.CloudEventsHttpExtension`
**Name:** "Cloud events HTTP"

**Overview:** No overview provided.


##### Configuration: 

| Key                               | Required | Type     | Default | Pattern | Min | Max | Description |
| --------------------------------- | -------- | -------- | ------- | ------- | --- | --- | ----------- |
| `edc.events.cloudevents.endpoint` | `*`      | `string` | ``      |         |     |     |             |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.spi.event.EventRouter` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.system.Hostname` (required)

Module `org.eclipse.edc:iam-mock:0.9.0`
---------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.mock.IamMockExtension`
**Name:** "Mock IAM"

**Overview:**  An IAM provider mock used for testing.



##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.spi.iam.IdentityService`
- `org.eclipse.edc.spi.iam.AudienceResolver`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:identity-did-core:0.9.0`
------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.did.IdentityDidCoreExtension`
**Name:** "Identity Did Core"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.iam.did.spi.resolution.DidResolverRegistry`
- `org.eclipse.edc.iam.did.spi.resolution.DidPublicKeyResolver`

##### Referenced (injected) services:
- `org.eclipse.edc.keys.spi.KeyParserRegistry` (required)

Module `IAM DID services:0.9.0`
-------------------------------
_org.eclipse.edc:identity-did-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.iam.did.spi.resolution.DidPublicKeyResolver`
  - `org.eclipse.edc.iam.did.spi.resolution.DidResolverRegistry`
  - `org.eclipse.edc.iam.did.spi.credentials.CredentialsVerifier`
  - `org.eclipse.edc.iam.did.spi.store.DidStore`

### Extensions
Module `org.eclipse.edc:identity-did-web:0.9.0`
-----------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.did.web.WebDidExtension`
**Name:** "Web DID"

**Overview:**  Initializes support for resolving Web DIDs.



##### Configuration: 

| Key                         | Required | Type     | Default | Pattern | Min | Max | Description |
| --------------------------- | -------- | -------- | ------- | ------- | --- | --- | ----------- |
| `edc.webdid.doh.url`        |          | `string` | ``      |         |     |     |             |
| `edc.iam.did.web.use.https` |          | `string` | ``      |         |     |     |             |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.iam.did.spi.resolution.DidResolverRegistry` (required)
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:identity-trust-core:0.9.0`
--------------------------------------------------

_Categories: iam,transform,jsonld,iam,transform,jsonld_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.identitytrust.core.IdentityAndTrustExtension`
**Name:** "Identity And Trust Extension"

**Overview:** No overview provided.


##### Configuration: 

| Key                                            | Required | Type     | Default  | Pattern | Min | Max | Description                                                                  |
| ---------------------------------------------- | -------- | -------- | -------- | ------- | --- | --- | ---------------------------------------------------------------------------- |
| `edc.iam.credential.revocation.cache.validity` |          | `long`   | `900000` |         |     |     | Validity period of cached StatusList2021 credential entries in milliseconds. |
| `edc.iam.issuer.id`                            | `*`      | `string` | ``       |         |     |     | DID of this connector                                                        |

##### Provided services:
- `org.eclipse.edc.spi.iam.IdentityService`
- `org.eclipse.edc.iam.identitytrust.spi.CredentialServiceClient`
- `org.eclipse.edc.iam.verifiablecredentials.spi.validation.PresentationVerifier`

##### Referenced (injected) services:
- `org.eclipse.edc.iam.identitytrust.spi.SecureTokenService` (required)
- `org.eclipse.edc.iam.verifiablecredentials.spi.validation.TrustedIssuerRegistry` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.iam.identitytrust.spi.verification.SignatureSuiteRegistry` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)
- `java.time.Clock` (required)
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.iam.did.spi.resolution.DidResolverRegistry` (required)
- `org.eclipse.edc.token.spi.TokenValidationService` (required)
- `org.eclipse.edc.token.spi.TokenValidationRulesRegistry` (required)
- `org.eclipse.edc.iam.did.spi.resolution.DidPublicKeyResolver` (required)
- `org.eclipse.edc.iam.identitytrust.spi.ClaimTokenCreatorFunction` (required)
- `org.eclipse.edc.spi.agent.ParticipantAgentService` (required)
- `org.eclipse.edc.iam.identitytrust.spi.DcpParticipantAgentServiceExtension` (required)
- `org.eclipse.edc.iam.verifiablecredentials.spi.model.RevocationServiceRegistry` (required)

#### Class: `org.eclipse.edc.iam.identitytrust.core.IdentityTrustTransformExtension`
**Name:** "Identity And Trust Transform Extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

#### Class: `org.eclipse.edc.iam.identitytrust.core.DcpScopeExtractorExtension`
**Name:** "DCP scope extractor extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.policy.engine.spi.PolicyEngine` (required)
- `org.eclipse.edc.iam.identitytrust.spi.scope.ScopeExtractorRegistry` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)

#### Class: `org.eclipse.edc.iam.identitytrust.core.DcpDefaultServicesExtension`
**Name:** "Identity And Trust Extension to register default services"

**Overview:** No overview provided.


##### Configuration: 

| Key                            | Required | Type     | Default                   | Pattern | Min | Max | Description                                                                                                   |
| ------------------------------ | -------- | -------- | ------------------------- | ------- | --- | --- | ------------------------------------------------------------------------------------------------------------- |
| `edc.iam.sts.privatekey.alias` |          | `string` | `A random EC private key` |         |     |     | Alias of private key used for signing tokens, retrieved from private key resolver                             |
| `edc.iam.sts.publickey.id`     |          | `string` | `A random EC public key`  |         |     |     | Id used by the counterparty to resolve the public key for token validation, e.g. did:example:123#public-key-0 |
| `edc.iam.sts.token.expiration` |          | `string` | `5`                       |         |     |     | Self-issued ID Token expiration in minutes. By default is 5 minutes                                           |

##### Provided services:
- `org.eclipse.edc.iam.identitytrust.spi.SecureTokenService`
- `org.eclipse.edc.iam.verifiablecredentials.spi.validation.TrustedIssuerRegistry`
- `org.eclipse.edc.iam.identitytrust.spi.verification.SignatureSuiteRegistry`
- `org.eclipse.edc.iam.identitytrust.spi.DcpParticipantAgentServiceExtension`
- `org.eclipse.edc.iam.identitytrust.spi.scope.ScopeExtractorRegistry`
- `org.eclipse.edc.spi.iam.AudienceResolver`
- `org.eclipse.edc.iam.identitytrust.spi.ClaimTokenCreatorFunction`

##### Referenced (injected) services:
- `java.time.Clock` (required)
- `org.eclipse.edc.jwt.signer.spi.JwsSignerProvider` (required)

Module `org.eclipse.edc:identity-trust-issuers-configuration:0.9.0`
-------------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.identitytrust.issuer.configuration.TrustedIssuerConfigurationExtension`
**Name:** "Trusted Issuers Configuration Extensions"

**Overview:**  This DCP extension makes it possible to configure a list of trusted issuers, that will be matched against the Verifiable Credential issuers.



##### Configuration: 

| Key                                               | Required | Type     | Default | Pattern | Min | Max | Description                          |
| ------------------------------------------------- | -------- | -------- | ------- | ------- | --- | --- | ------------------------------------ |
| `edc.iam.trusted-issuer.<issuerAlias>.properties` |          | `string` | ``      |         |     |     | Additional properties of the issuer. |
| `edc.iam.trusted-issuer.<issuerAlias>.id`         | `*`      | `string` | ``      |         |     |     | ID of the issuer.                    |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.iam.verifiablecredentials.spi.validation.TrustedIssuerRegistry` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)

Module `org.eclipse.edc:identity-trust-sts-api:0.9.0`
-----------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.api.iam.identitytrust.sts.SecureTokenServiceApiExtension`
**Name:** "Secure Token Service API"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.iam.identitytrust.sts.spi.service.StsClientService` (required)
- `org.eclipse.edc.iam.identitytrust.sts.spi.service.StsClientTokenGeneratorService` (required)
- `org.eclipse.edc.web.spi.WebService` (required)

#### Class: `org.eclipse.edc.api.iam.identitytrust.sts.StsApiConfigurationExtension`
**Name:** "Secure Token Service API configuration"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebServer` (required)
- `org.eclipse.edc.web.spi.configuration.WebServiceConfigurer` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.spi.system.apiversion.ApiVersionService` (required)

Module `org.eclipse.edc:identity-trust-sts-client-configuration:0.9.0`
----------------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.identitytrust.sts.client.configuration.StsClientConfigurationExtension`
**Name:** "STS Client Configuration extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.spi.monitor.Monitor` (required)
- `org.eclipse.edc.iam.identitytrust.sts.spi.store.StsClientStore` (required)

Module `org.eclipse.edc:identity-trust-sts-core:0.9.0`
------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.identitytrust.sts.defaults.StsDefaultStoresExtension`
**Name:** "Secure Token Service Default Stores"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.iam.identitytrust.sts.spi.store.StsClientStore`

##### Referenced (injected) services:
_None_

#### Class: `org.eclipse.edc.iam.identitytrust.sts.defaults.StsDefaultServicesExtension`
**Name:** "Secure Token Service Default Services"

**Overview:** No overview provided.


##### Configuration: 

| Key                            | Required | Type     | Default | Pattern | Min | Max | Description                                                         |
| ------------------------------ | -------- | -------- | ------- | ------- | --- | --- | ------------------------------------------------------------------- |
| `edc.iam.sts.token.expiration` |          | `string` | `5`     |         |     |     | Self-issued ID Token expiration in minutes. By default is 5 minutes |

##### Provided services:
- `org.eclipse.edc.iam.identitytrust.sts.spi.service.StsClientTokenGeneratorService`
- `org.eclipse.edc.iam.identitytrust.sts.spi.service.StsClientService`

##### Referenced (injected) services:
- `org.eclipse.edc.iam.identitytrust.sts.spi.store.StsClientStore` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.spi.security.Vault` (required)
- `org.eclipse.edc.jwt.signer.spi.JwsSignerProvider` (required)
- `java.time.Clock` (required)

Module `org.eclipse.edc:identity-trust-sts-remote-client:0.9.0`
---------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.identitytrust.sts.remote.client.StsRemoteClientConfigurationExtension`
**Name:** "Sts remote client configuration extension"

**Overview:**  Configuration Extension for the STS OAuth2 client



##### Configuration: 

| Key                                     | Required | Type     | Default | Pattern | Min | Max | Description                                |
| --------------------------------------- | -------- | -------- | ------- | ------- | --- | --- | ------------------------------------------ |
| `edc.iam.sts.oauth.token.url`           |          | `string` | ``      |         |     |     | STS OAuth2 endpoint for requesting a token |
| `edc.iam.sts.oauth.client.id`           |          | `string` | ``      |         |     |     | STS OAuth2 client id                       |
| `edc.iam.sts.oauth.client.secret.alias` |          | `string` | ``      |         |     |     | Vault alias of STS OAuth2 client secret    |

##### Provided services:
- `org.eclipse.edc.iam.identitytrust.sts.remote.StsRemoteClientConfiguration`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.security.Vault` (required)

#### Class: `org.eclipse.edc.iam.identitytrust.sts.remote.client.StsRemoteClientExtension`
**Name:** "Sts remote client configuration extension"

**Overview:**  Configuration Extension for the STS OAuth2 client



##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.iam.identitytrust.spi.SecureTokenService`

##### Referenced (injected) services:
- `org.eclipse.edc.iam.identitytrust.sts.remote.StsRemoteClientConfiguration` (required)
- `org.eclipse.edc.iam.oauth2.spi.client.Oauth2Client` (required)
- `org.eclipse.edc.spi.security.Vault` (required)

Module `org.eclipse.edc:jersey-core:0.9.0`
------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.web.jersey.JerseyExtension`
**Name:** "JerseyExtension"

##### Configuration: 

| Key                         | Required | Type     | Default | Pattern | Min | Max | Description |
| --------------------------- | -------- | -------- | ------- | ------- | --- | --- | ----------- |
| `edc.web.rest.cors.origins` |          | `string` | ``      |         |     |     |             |
| `edc.web.rest.cors.enabled` |          | `string` | ``      |         |     |     |             |
| `edc.web.rest.cors.headers` |          | `string` | ``      |         |     |     |             |
| `edc.web.rest.cors.methods` |          | `string` | ``      |         |     |     |             |

##### Provided services:
- `org.eclipse.edc.web.spi.WebService`
- `org.eclipse.edc.web.spi.validation.InterceptorFunctionRegistry`

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebServer` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:jersey-micrometer:0.9.0`
------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.web.jersey.micrometer.JerseyMicrometerExtension`
**Name:** "JerseyMicrometerExtension"

##### Configuration: 

| Key                          | Required | Type     | Default | Pattern | Min | Max | Description |
| ---------------------------- | -------- | -------- | ------- | ------- | --- | --- | ----------- |
| `edc.metrics.enabled`        |          | `string` | ``      |         |     |     |             |
| `edc.metrics.jersey.enabled` |          | `string` | ``      |         |     |     |             |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `io.micrometer.core.instrument.MeterRegistry` (required)

Module `org.eclipse.edc:jetty-core:0.9.0`
-----------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.web.jetty.JettyExtension`
**Name:** "JettyExtension"

##### Configuration: 

| Key                                 | Required | Type     | Default | Pattern | Min | Max | Description |
| ----------------------------------- | -------- | -------- | ------- | ------- | --- | --- | ----------- |
| `edc.web.https.keystore.password`   |          | `string` | ``      |         |     |     |             |
| `edc.web.https.keymanager.password` |          | `string` | ``      |         |     |     |             |
| `edc.web.https.keystore.path`       |          | `string` | ``      |         |     |     |             |
| `edc.web.https.keystore.type`       |          | `string` | ``      |         |     |     |             |

##### Provided services:
- `org.eclipse.edc.web.spi.WebServer`
- `org.eclipse.edc.web.jetty.JettyService`
- `org.eclipse.edc.web.spi.configuration.WebServiceConfigurer`

##### Referenced (injected) services:
_None_

Module `org.eclipse.edc:jetty-micrometer:0.9.0`
-----------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.web.jetty.micrometer.JettyMicrometerExtension`
**Name:** "Jetty Micrometer Metrics"

**Overview:**  An extension that registers Micrometer {@link JettyConnectionMetrics} into Jetty to
 provide server metrics.



##### Configuration: 

| Key                         | Required | Type     | Default | Pattern | Min | Max | Description |
| --------------------------- | -------- | -------- | ------- | ------- | --- | --- | ----------- |
| `edc.metrics.enabled`       |          | `string` | ``      |         |     |     |             |
| `edc.metrics.jetty.enabled` |          | `string` | ``      |         |     |     |             |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.jetty.JettyService` (required)
- `io.micrometer.core.instrument.MeterRegistry` (required)

Module `org.eclipse.edc:json-ld:0.9.0`
--------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.jsonld.JsonLdExtension`
**Name:** "JSON-LD Extension"

**Overview:**  Adds support for working with JSON-LD. Provides an ObjectMapper that works with Jakarta JSON-P
 types through the TypeManager context {@link CoreConstants#JSON_LD} and a registry
 for {@link JsonLdTransformer}s. The module also offers
 functions for working with JSON-LD structures.



##### Configuration: 

| Key                                        | Required | Type      | Default | Pattern | Min | Max | Description                                                                                     |
| ------------------------------------------ | -------- | --------- | ------- | ------- | --- | --- | ----------------------------------------------------------------------------------------------- |
| `edc.jsonld.document.<documentAlias>.path` | `*`      | `string`  | ``      |         |     |     | Path of the JSON-LD document to cache                                                           |
| `edc.jsonld.document.<documentAlias>.url`  | `*`      | `string`  | ``      |         |     |     | URL of the JSON-LD document to cache                                                            |
| `edc.jsonld.http.enabled`                  |          | `boolean` | `false` |         |     |     | If set enable http json-ld document resolution                                                  |
| `edc.jsonld.https.enabled`                 |          | `boolean` | `false` |         |     |     | If set enable https json-ld document resolution                                                 |
| `edc.jsonld.vocab.disable`                 |          | `boolean` | `false` |         |     |     | If true disable the @vocab context definition. This could be used to avoid api breaking changes |
| `edc.jsonld.prefixes.check`                |          | `boolean` | `true`  |         |     |     | If true a validation on expended object will be made against configured prefixes                |

##### Provided services:
- `org.eclipse.edc.jsonld.spi.JsonLd`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `Implementation SPI that is used to contribute custom JWSSigners to the JwtGenerationService:0.9.0`
----------------------------------------------------------------------------------------------------------
_org.eclipse.edc:jwt-signer-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.jwt.signer.spi.JwsSignerProvider`

### Extensions
Module `JTW services:0.9.0`
---------------------------
_org.eclipse.edc:jwt-spi_

_Categories: None_

### Extension points
_None_

### Extensions
Module `org.eclipse.edc:management-api-configuration:0.9.0`
-----------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.api.management.configuration.ManagementApiConfigurationExtension`
**Name:** "Management API configuration"

**Overview:**  Configure 'management' api context.



##### Configuration: 

| Key                       | Required | Type     | Default                                      | Pattern | Min | Max | Description                                          |
| ------------------------- | -------- | -------- | -------------------------------------------- | ------- | --- | --- | ---------------------------------------------------- |
| `edc.management.endpoint` |          | `string` | `<hostname:management.port/management.path>` |         |     |     | Configures endpoint for reaching the Management API. |

##### Provided services:
- `org.eclipse.edc.web.spi.configuration.context.ManagementApiUrl`

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.web.spi.WebServer` (required)
- `org.eclipse.edc.api.auth.spi.registry.ApiAuthenticationRegistry` (required)
- `org.eclipse.edc.web.spi.configuration.WebServiceConfigurer` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.spi.agent.ParticipantIdMapper` (required)
- `org.eclipse.edc.spi.system.Hostname` (required)
- `org.eclipse.edc.spi.system.apiversion.ApiVersionService` (required)

Module `org.eclipse.edc:management-api-json-ld-context:0.9.0`
-------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.api.management.jsonld.ManagementApiJsonLdContextExtension`
**Name:** "ManagementApiJsonLdContextExtension"

##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.jsonld.spi.JsonLd` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)

Module `org.eclipse.edc:micrometer-core:0.9.0`
----------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.metrics.micrometer.MicrometerExtension`
**Name:** "Micrometer Metrics"

**Overview:** No overview provided.


##### Configuration: 

| Key                            | Required | Type     | Default | Pattern | Min | Max | Description |
| ------------------------------ | -------- | -------- | ------- | ------- | --- | --- | ----------- |
| `edc.metrics.enabled`          |          | `string` | ``      |         |     |     |             |
| `edc.metrics.system.enabled`   |          | `string` | ``      |         |     |     |             |
| `edc.metrics.okhttp.enabled`   |          | `string` | ``      |         |     |     |             |
| `edc.metrics.executor.enabled` |          | `string` | ``      |         |     |     |             |

##### Provided services:
- `okhttp3.EventListener`
- `org.eclipse.edc.spi.system.ExecutorInstrumentation`
- `io.micrometer.core.instrument.MeterRegistry`

##### Referenced (injected) services:
_None_

Module `org.eclipse.edc:monitor-jdk-logger:0.9.0`
-------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.monitor.logger.LoggerMonitorExtension`
**Name:** "Logger monitor"

**Overview:**  Extension adding logging monitor.



##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
_None_

Module `org.eclipse.edc:oauth2-client:0.9.0`
--------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.oauth2.client.Oauth2ClientExtension`
**Name:** "OAuth2 Client"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.iam.oauth2.spi.client.Oauth2Client`

##### Referenced (injected) services:
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:oauth2-core:0.9.0`
------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.oauth2.Oauth2ServiceExtension`
**Name:** "OAuth2 Identity Service"

**Overview:**  Provides OAuth2 client credentials flow support.



##### Configuration: 

| Key                                     | Required | Type     | Default | Pattern | Min | Max | Description                                                                                   |
| --------------------------------------- | -------- | -------- | ------- | ------- | --- | --- | --------------------------------------------------------------------------------------------- |
| `edc.oauth.provider.jwks.url`           |          | `string` | ``      |         |     |     |                                                                                               |
| `edc.oauth.provider.audience`           |          | `string` | ``      |         |     |     | outgoing tokens 'aud' claim value, by default it's the connector id                           |
| `edc.oauth.endpoint.audience`           |          | `string` | ``      |         |     |     | incoming tokens 'aud' claim required value, by default it's the provider audience value       |
| `edc.oauth.certificate.alias`           |          | `string` | ``      |         |     |     |                                                                                               |
| `edc.oauth.private.key.alias`           |          | `string` | ``      |         |     |     |                                                                                               |
| `edc.oauth.provider.jwks.refresh`       |          | `string` | ``      |         |     |     |                                                                                               |
| `edc.oauth.token.url`                   |          | `string` | ``      |         |     |     |                                                                                               |
| `edc.oauth.token.expiration`            |          | `string` | ``      |         |     |     | Token expiration in minutes. By default is 5 minutes                                          |
| `edc.oauth.client.id`                   |          | `string` | ``      |         |     |     |                                                                                               |
| `edc.oauth.validation.nbf.leeway`       |          | `int`    | `10`    |         |     |     | Leeway in seconds for validating the not before (nbf) claim in the token.                     |
| `edc.oauth.validation.issued.at.leeway` |          | `int`    | `0`     |         |     |     | Leeway in seconds for validating the issuedAt claim in the token. By default it is 0 seconds. |

##### Provided services:
- `org.eclipse.edc.spi.iam.IdentityService`

##### Referenced (injected) services:
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.keys.spi.PrivateKeyResolver` (required)
- `org.eclipse.edc.keys.spi.CertificateResolver` (required)
- `java.time.Clock` (required)
- `org.eclipse.edc.iam.oauth2.spi.client.Oauth2Client` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.token.spi.TokenValidationRulesRegistry` (required)
- `org.eclipse.edc.token.spi.TokenValidationService` (required)
- `org.eclipse.edc.token.spi.TokenDecoratorRegistry` (required)
- `org.eclipse.edc.jwt.signer.spi.JwsSignerProvider` (required)

#### Class: `org.eclipse.edc.iam.oauth2.Oauth2ServiceDefaultServicesExtension`
**Name:** "Oauth2ServiceDefaultServicesExtension"

**Overview:**  Provides OAuth2 client credentials flow support.



##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.spi.iam.AudienceResolver`

##### Referenced (injected) services:
_None_

Module `org.eclipse.edc:oauth2-daps:0.9.0`
------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.oauth2.daps.DapsExtension`
**Name:** "DAPS"

**Overview:**  Provides specialization of Oauth2 extension to interact with DAPS instance



##### Configuration: 

| Key                   | Required | Type     | Default                             | Pattern | Min | Max | Description                                                         |
| --------------------- | -------- | -------- | ----------------------------------- | ------- | --- | --- | ------------------------------------------------------------------- |
| `edc.iam.token.scope` |          | `string` | `idsc:IDS_CONNECTOR_ATTRIBUTES_ALL` |         |     |     | The value of the scope claim that is passed to DAPS to obtain a DAT |

##### Provided services:
- `org.eclipse.edc.token.spi.TokenDecorator`

##### Referenced (injected) services:
- `org.eclipse.edc.token.spi.TokenDecoratorRegistry` (required)

Module `OAuth2 services:0.9.0`
------------------------------
_org.eclipse.edc:oauth2-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.iam.oauth2.spi.client.Oauth2Client`

### Extensions
Module `org.eclipse.edc:policy-definition-api:0.9.0`
----------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.api.management.policy.PolicyDefinitionApiExtension`
**Name:** "Management API: Policy Definition"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.policydefinition.PolicyDefinitionService` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:policy-definition-store-sql:0.9.0`
----------------------------------------------------------

_Categories: None_

### Extension points
  - `org.eclipse.edc.connector.controlplane.store.sql.policydefinition.store.schema.SqlPolicyStoreStatements`

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.store.sql.policydefinition.SqlPolicyStoreExtension`
**Name:** "SQL policy store"

**Overview:** No overview provided.


##### Configuration: 

| Key                               | Required | Type     | Default   | Pattern | Min | Max | Description               |
| --------------------------------- | -------- | -------- | --------- | ------- | --- | --- | ------------------------- |
| `edc.sql.store.policy.datasource` |          | `string` | `default` |         |     |     | The datasource to be used |

##### Provided services:
- `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyDefinitionStore`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.connector.controlplane.store.sql.policydefinition.store.schema.SqlPolicyStoreStatements` (optional)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper` (required)

Module `Policy Engine services:0.9.0`
-------------------------------------
_org.eclipse.edc:policy-engine-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.policy.engine.spi.PolicyEngine`
  - `org.eclipse.edc.policy.engine.spi.RuleBindingRegistry`

### Extensions
Module `org.eclipse.edc:policy-monitor-core:0.9.0`
--------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.policy.monitor.PolicyMonitorDefaultServicesExtension`
**Name:** "PolicyMonitor Default Services"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.policy.monitor.spi.PolicyMonitorStore`

##### Referenced (injected) services:
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.query.CriterionOperatorRegistry` (required)

#### Class: `org.eclipse.edc.connector.policy.monitor.PolicyMonitorExtension`
**Name:** "Policy Monitor"

**Overview:** No overview provided.


##### Configuration: 

| Key                                                      | Required | Type   | Default | Pattern | Min | Max | Description                                                                                     |
| -------------------------------------------------------- | -------- | ------ | ------- | ------- | --- | --- | ----------------------------------------------------------------------------------------------- |
| `edc.policy.monitor.state-machine.iteration-wait-millis` |          | `long` | ``      |         |     |     | the iteration wait time in milliseconds in the policy monitor state machine. Default value 1000 |
| `edc.policy.monitor.state-machine.batch-size`            |          | `int`  | ``      |         |     |     | the batch size in the policy monitor state machine. Default value 20                            |

##### Provided services:
- `org.eclipse.edc.connector.policy.monitor.spi.PolicyMonitorManager`

##### Referenced (injected) services:
- `org.eclipse.edc.spi.system.ExecutorInstrumentation` (required)
- `org.eclipse.edc.spi.telemetry.Telemetry` (required)
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.event.EventRouter` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.contractagreement.ContractAgreementService` (required)
- `org.eclipse.edc.policy.engine.spi.PolicyEngine` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.transferprocess.TransferProcessService` (required)
- `org.eclipse.edc.connector.policy.monitor.spi.PolicyMonitorStore` (required)
- `org.eclipse.edc.policy.engine.spi.RuleBindingRegistry` (required)

Module `org.eclipse.edc:policy-monitor-store-sql:0.9.0`
-------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.policy.monitor.store.sql.SqlPolicyMonitorStoreExtension`
**Name:** "SqlPolicyMonitorStoreExtension"

##### Configuration: 

| Key                                       | Required | Type     | Default   | Pattern | Min | Max | Description                                                      |
| ----------------------------------------- | -------- | -------- | --------- | ------- | --- | --- | ---------------------------------------------------------------- |
| ~~edc.datasource.policy-monitor.name~~    |          | `string` | `default` |         |     |     | Name of the datasource to use for accessing policy monitor store |
| `edc.sql.store.policy-monitor.datasource` |          | `string` | `default` |         |     |     | The datasource to be used                                        |

##### Provided services:
- `org.eclipse.edc.connector.policy.monitor.spi.PolicyMonitorStore`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.connector.policy.monitor.store.sql.schema.PolicyMonitorStatements` (optional)
- `java.time.Clock` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper` (required)

Module `Policy services:0.9.0`
------------------------------
_org.eclipse.edc:policy-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyArchive`
  - `org.eclipse.edc.connector.controlplane.policy.spi.store.PolicyDefinitionStore`

### Extensions
Module `org.eclipse.edc:provision-http:0.9.0`
---------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.provision.http.HttpWebhookExtension`
**Name:** "HttpWebhookExtension"

**Overview:**  The HTTP Provisioner extension delegates to HTTP endpoints to perform provision operations.



##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.connector.controlplane.provision.http.HttpProvisionerWebhookUrl`

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.transferprocess.TransferProcessService` (required)
- `org.eclipse.edc.web.spi.configuration.context.ManagementApiUrl` (required)

#### Class: `org.eclipse.edc.connector.controlplane.provision.http.HttpProvisionerExtension`
**Name:** "HTTP Provisioning"

**Overview:**  The HTTP Provisioner extension delegates to HTTP endpoints to perform provision operations.



##### Configuration: 

| Key                 | Required | Type     | Default            | Pattern | Min | Max | Description |
| ------------------- | -------- | -------- | ------------------ | ------- | --- | --- | ----------- |
| `provisioner.type`  | `*`      | `string` | ``                 |         |     |     |             |
| `data.address.type` | `*`      | `string` | ``                 |         |     |     |             |
| `endpoint`          | `*`      | `string` | ``                 |         |     |     |             |
| `policy.scope`      |          | `string` | `http.provisioner` |         |     |     |             |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.transfer.spi.provision.ProvisionManager` (required)
- `org.eclipse.edc.policy.engine.spi.PolicyEngine` (required)
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.provision.ResourceManifestGenerator` (required)
- `org.eclipse.edc.connector.controlplane.provision.http.HttpProvisionerWebhookUrl` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.validator.spi.DataAddressValidatorRegistry` (required)

Module `org.eclipse.edc:secrets-api:0.9.0`
------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.api.management.secret.SecretsApiExtension`
**Name:** "Management API: Secret"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.connector.spi.service.SecretService` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)

Module `org.eclipse.edc:sql-bootstrapper:0.9.0`
-----------------------------------------------

_Categories: sql,persistence,storage,sql,persistence,storage_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapperExtension`
**Name:** "SQL Schema Bootstrapper Extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)

Module `org.eclipse.edc:sql-core:0.9.0`
---------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.sql.SqlCoreExtension`
**Name:** "SQL Core"

**Overview:** No overview provided.


##### Configuration: 

| Key                  | Required | Type     | Default | Pattern | Min | Max | Description                          |
| -------------------- | -------- | -------- | ------- | ------- | --- | --- | ------------------------------------ |
| `edc.sql.fetch.size` |          | `string` | `5000`  |         |     |     | Fetch size value used in SQL queries |

##### Provided services:
- `org.eclipse.edc.sql.QueryExecutor`
- `org.eclipse.edc.sql.ConnectionFactory`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)

Module `org.eclipse.edc:sql-pool-apache-commons:0.9.0`
------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.sql.pool.commons.CommonsConnectionPoolServiceExtension`
**Name:** "Commons Connection Pool"

**Overview:** No overview provided.


##### Configuration: 

| Key                                                    | Required | Type      | Default | Pattern | Min | Max | Description                                                                                                                 |
| ------------------------------------------------------ | -------- | --------- | ------- | ------- | --- | --- | --------------------------------------------------------------------------------------------------------------------------- |
| `edc.datasource.<name>url`                             | `*`      | `string`  | ``      |         |     |     | JDBC url                                                                                                                    |
| `edc.datasource.<name>user`                            |          | `string`  | ``      |         |     |     | Username to be used for the JDBC connection. Can be omitted if not required, or if the user is encoded in the JDBC url.     |
| `edc.datasource.<name>password`                        |          | `string`  | ``      |         |     |     | Username to be used for the JDBC connection. Can be omitted if not required, or if the password is encoded in the JDBC url. |
| `edc.datasource.<name>pool.connections.max-idle`       |          | `int`     | ``      |         |     |     | Pool max idle connections                                                                                                   |
| `edc.datasource.<name>pool.connections.max-total`      |          | `int`     | ``      |         |     |     | Pool max total connections                                                                                                  |
| `edc.datasource.<name>pool.connections.min-idle`       |          | `int`     | ``      |         |     |     | Pool min idle connections                                                                                                   |
| `edc.datasource.<name>pool.connection.test.on-borrow`  |          | `boolean` | ``      |         |     |     | Pool test on borrow                                                                                                         |
| `edc.datasource.<name>pool.connection.test.on-create`  |          | `boolean` | ``      |         |     |     | Pool test on create                                                                                                         |
| `edc.datasource.<name>pool.connection.test.on-return`  |          | `boolean` | ``      |         |     |     | Pool test on return                                                                                                         |
| `edc.datasource.<name>pool.connection.test.while-idle` |          | `boolean` | ``      |         |     |     | Pool test while idle                                                                                                        |
| `edc.datasource.<name>pool.connection.test.query`      |          | `string`  | ``      |         |     |     | Pool test query                                                                                                             |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.spi.monitor.Monitor` (required)
- `org.eclipse.edc.sql.ConnectionFactory` (required)
- `org.eclipse.edc.spi.security.Vault` (required)

Module `org.eclipse.edc:sts-server:0.9.0`
-----------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.identitytrust.sts.server.StsVaultSeedExtension`
**Name:** "StsVaultSeedExtension"

##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.spi.security.Vault` (required)

Module `org.eclipse.edc:token-core:0.9.0`
-----------------------------------------

_Categories: token,security,auth,token,security,auth_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.token.TokenServicesExtension`
**Name:** "Token Services Extension"

**Overview:**  This extension registers the {@link TokenValidationService} and the {@link TokenValidationRulesRegistry}
 which can then be used by downstream modules.



##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.token.spi.TokenValidationRulesRegistry`
- `org.eclipse.edc.token.spi.TokenValidationService`
- `org.eclipse.edc.token.spi.TokenDecoratorRegistry`
- `org.eclipse.edc.jwt.signer.spi.JwsSignerProvider`

##### Referenced (injected) services:
- `org.eclipse.edc.keys.spi.PrivateKeyResolver` (required)

Module `Token services:0.9.0`
-----------------------------
_org.eclipse.edc:token-spi_

_Categories: None_

### Extension points
_None_

### Extensions
Module `org.eclipse.edc:transaction-atomikos:0.9.0`
---------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.transaction.atomikos.AtomikosTransactionExtension`
**Name:** "Atomikos Transaction"

**Overview:**  Provides an implementation of a {@link DataSourceRegistry} and a {@link TransactionContext} backed by Atomikos.



##### Configuration: 

| Key                                | Required | Type     | Default | Pattern | Min | Max | Description |
| ---------------------------------- | -------- | -------- | ------- | ------- | --- | --- | ----------- |
| `driver.class`                     | `*`      | `string` | ``      |         |     |     |             |
| `url`                              | `*`      | `string` | ``      |         |     |     |             |
| `type`                             |          | `string` | ``      |         |     |     |             |
| `username`                         |          | `string` | ``      |         |     |     |             |
| `password`                         |          | `string` | ``      |         |     |     |             |
| `pool.size`                        |          | `string` | ``      |         |     |     |             |
| `max.pool.size`                    |          | `string` | ``      |         |     |     |             |
| `min.pool.size`                    |          | `string` | ``      |         |     |     |             |
| `connection.timeout`               |          | `string` | ``      |         |     |     |             |
| `login.timeout`                    |          | `string` | ``      |         |     |     |             |
| `maintenance.interval`             |          | `string` | ``      |         |     |     |             |
| `max.idle`                         |          | `string` | ``      |         |     |     |             |
| `query`                            |          | `string` | ``      |         |     |     |             |
| `properties`                       |          | `string` | ``      |         |     |     |             |
| `edc.atomikos.timeout`             |          | `string` | ``      |         |     |     |             |
| `edc.atomikos.directory`           |          | `string` | ``      |         |     |     |             |
| `edc.atomikos.threaded2pc`         |          | `string` | ``      |         |     |     |             |
| `edc.atomikos.logging`             |          | `string` | ``      |         |     |     |             |
| `edc.atomikos.checkpoint.interval` |          | `string` | ``      |         |     |     |             |

##### Provided services:
- `org.eclipse.edc.transaction.spi.TransactionContext`
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry`

##### Referenced (injected) services:
_None_

Module `DataSource services:0.9.0`
----------------------------------
_org.eclipse.edc:transaction-datasource-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry`

### Extensions
Module `org.eclipse.edc:transaction-local:0.9.0`
------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.transaction.local.LocalTransactionExtension`
**Name:** "Local Transaction"

**Overview:**  Support for transaction context backed by one or more local resources, including a {@link DataSourceRegistry}.



##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry`
- `org.eclipse.edc.transaction.spi.TransactionContext`

##### Referenced (injected) services:
_None_

Module `Transactional context services:0.9.0`
---------------------------------------------
_org.eclipse.edc:transaction-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.transaction.spi.TransactionContext`

### Extensions
Module `org.eclipse.edc:transfer-data-plane-signaling:0.9.0`
------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.transfer.dataplane.TransferDataPlaneSignalingExtension`
**Name:** "Transfer Data Plane Signaling Extension"

**Overview:** No overview provided.


##### Configuration: 

| Key                                      | Required | Type     | Default  | Pattern | Min | Max | Description                                                                                              |
| ---------------------------------------- | -------- | -------- | -------- | ------- | --- | --- | -------------------------------------------------------------------------------------------------------- |
| `edc.dataplane.client.selector.strategy` |          | `string` | `random` |         |     |     | Defines strategy for Data Plane instance selection in case Data Plane is not embedded in current runtime |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.transfer.spi.flow.DataFlowManager` (required)
- `org.eclipse.edc.web.spi.configuration.context.ControlApiUrl` (optional)
- `org.eclipse.edc.connector.dataplane.selector.spi.DataPlaneSelectorService` (required)
- `org.eclipse.edc.connector.dataplane.selector.spi.client.DataPlaneClientFactory` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.flow.DataFlowPropertiesProvider` (optional)
- `org.eclipse.edc.connector.controlplane.transfer.spi.flow.TransferTypeParser` (required)

Module `Transfer data plane services:0.9.0`
-------------------------------------------
_org.eclipse.edc:transfer-data-plane-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.connector.controlplane.transfer.dataplane.spi.security.DataEncrypter`

### Extensions
Module `org.eclipse.edc:transfer-process-api:0.9.0`
---------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.api.management.transferprocess.TransferProcessApiExtension`
**Name:** "Management API: Transfer Process"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.transform.spi.TypeTransformerRegistry` (required)
- `org.eclipse.edc.connector.controlplane.services.spi.transferprocess.TransferProcessService` (required)
- `org.eclipse.edc.validator.spi.JsonObjectValidatorRegistry` (required)

Module `org.eclipse.edc:transfer-process-store-sql:0.9.0`
---------------------------------------------------------

_Categories: None_

### Extension points
  - `org.eclipse.edc.connector.controlplane.store.sql.transferprocess.store.schema.TransferProcessStoreStatements`

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.store.sql.transferprocess.SqlTransferProcessStoreExtension`
**Name:** "SQL transfer process store"

**Overview:** No overview provided.


##### Configuration: 

| Key                                        | Required | Type     | Default   | Pattern | Min | Max | Description               |
| ------------------------------------------ | -------- | -------- | --------- | ------- | --- | --- | ------------------------- |
| `edc.sql.store.transferprocess.datasource` |          | `string` | `default` |         |     |     | The datasource to be used |

##### Provided services:
- `org.eclipse.edc.connector.controlplane.transfer.spi.store.TransferProcessStore`

##### Referenced (injected) services:
- `org.eclipse.edc.transaction.datasource.spi.DataSourceRegistry` (required)
- `org.eclipse.edc.transaction.spi.TransactionContext` (required)
- `java.time.Clock` (required)
- `org.eclipse.edc.connector.controlplane.store.sql.transferprocess.store.schema.TransferProcessStoreStatements` (optional)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.sql.QueryExecutor` (required)
- `org.eclipse.edc.sql.bootstrapper.SqlSchemaBootstrapper` (required)

Module `org.eclipse.edc:transfer-pull-http-dynamic-receiver:0.9.0`
------------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.receiver.http.dynamic.HttpDynamicEndpointDataReferenceReceiverExtension`
**Name:** "Http Dynamic Endpoint Data Reference Receiver"

**Overview:** No overview provided.


##### Configuration: 

| Key                                   | Required | Type     | Default | Pattern | Min | Max | Description                                                    |
| ------------------------------------- | -------- | -------- | ------- | ------- | --- | --- | -------------------------------------------------------------- |
| `edc.receiver.http.dynamic.endpoint`  |          | `string` | ``      |         |     |     | Fallback endpoint when url is missing the the transfer process |
| `edc.receiver.http.dynamic.auth-key`  |          | `string` | ``      |         |     |     | Header name that will be sent with the EDR                     |
| `edc.receiver.http.dynamic.auth-code` |          | `string` | ``      |         |     |     | Header value that will be sent with the EDR                    |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.transfer.spi.edr.EndpointDataReferenceReceiverRegistry` (required)
- `okhttp3.OkHttpClient` (required)
- `dev.failsafe.RetryPolicy<java.lang.Object>` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.store.TransferProcessStore` (required)
- `org.eclipse.edc.connector.controlplane.transfer.spi.observe.TransferProcessObservable` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `org.eclipse.edc:transfer-pull-http-receiver:0.9.0`
----------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.controlplane.receiver.http.HttpEndpointDataReferenceReceiverExtension`
**Name:** "Http Endpoint Data Reference Receiver"

**Overview:** No overview provided.


##### Configuration: 

| Key                           | Required | Type     | Default | Pattern | Min | Max | Description |
| ----------------------------- | -------- | -------- | ------- | ------- | --- | --- | ----------- |
| `edc.receiver.http.endpoint`  |          | `string` | ``      |         |     |     |             |
| `edc.receiver.http.auth-key`  |          | `string` | ``      |         |     |     |             |
| `edc.receiver.http.auth-code` |          | `string` | ``      |         |     |     |             |

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.connector.controlplane.transfer.spi.edr.EndpointDataReferenceReceiverRegistry` (required)
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)

Module `Transfer services:0.9.0`
--------------------------------
_org.eclipse.edc:transfer-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.connector.controlplane.transfer.spi.observe.TransferProcessObservable`
  - `org.eclipse.edc.connector.controlplane.transfer.spi.provision.ProvisionManager`
  - `org.eclipse.edc.connector.controlplane.transfer.spi.provision.ResourceManifestGenerator`
  - `org.eclipse.edc.connector.controlplane.transfer.spi.flow.DataFlowManager`
  - `org.eclipse.edc.connector.controlplane.transfer.spi.flow.DataFlowPropertiesProvider`
  - `org.eclipse.edc.connector.controlplane.transfer.spi.edr.EndpointDataReferenceReceiverRegistry`
  - `org.eclipse.edc.connector.controlplane.transfer.spi.store.TransferProcessStore`
  - `org.eclipse.edc.connector.controlplane.transfer.spi.TransferProcessPendingGuard`
  - `org.eclipse.edc.connector.controlplane.transfer.spi.TransferProcessManager`

### Extensions
Module `org.eclipse.edc:validator-data-address-http-data:0.9.0`
---------------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.validator.dataaddress.httpdata.HttpDataDataAddressValidatorExtension`
**Name:** "DataAddress HttpData Validator"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.validator.spi.DataAddressValidatorRegistry` (required)

Module `org.eclipse.edc:validator-data-address-kafka:0.9.0`
-----------------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.validator.dataaddress.kafka.KafkaDataAddressValidatorExtension`
**Name:** "DataAddress Kafka Validator"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.validator.spi.DataAddressValidatorRegistry` (required)

Module `org.eclipse.edc:vault-hashicorp:0.9.0`
----------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.vault.hashicorp.HashicorpVaultExtension`
**Name:** "Hashicorp Vault"

**Overview:** No overview provided.


##### Configuration: 

| Key                                                 | Required | Type      | Default          | Pattern | Min | Max | Description                                                                                                                        |
| --------------------------------------------------- | -------- | --------- | ---------------- | ------- | --- | --- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `edc.vault.hashicorp.url`                           | `*`      | `string`  | ``               |         |     |     | The URL of the Hashicorp Vault                                                                                                     |
| `edc.vault.hashicorp.health.check.enabled`          |          | `boolean` | `true`           |         |     |     | Whether or not the vault health check is enabled                                                                                   |
| `edc.vault.hashicorp.api.health.check.path`         |          | `string`  | `/v1/sys/health` |         |     |     | The URL path of the vault's /health endpoint                                                                                       |
| `edc.vault.hashicorp.health.check.standby.ok`       |          | `boolean` | `false`          |         |     |     | Specifies if being a standby should still return the active status code instead of the standby status code                         |
| `edc.vault.hashicorp.token`                         | `*`      | `string`  | ``               |         |     |     | The token used to access the Hashicorp Vault                                                                                       |
| `edc.vault.hashicorp.token.scheduled-renew-enabled` |          | `string`  | `true`           |         |     |     | Whether the automatic token renewal process will be triggered or not. Should be disabled only for development and testing purposes |
| `edc.vault.hashicorp.token.ttl`                     |          | `long`    | `300`            |         |     |     | The time-to-live (ttl) value of the Hashicorp Vault token in seconds                                                               |
| `edc.vault.hashicorp.token.renew-buffer`            |          | `long`    | `30`             |         |     |     | The renew buffer of the Hashicorp Vault token in seconds                                                                           |
| `edc.vault.hashicorp.api.secret.path`               |          | `string`  | `/v1/secret`     |         |     |     | The URL path of the vault's /secret endpoint                                                                                       |

##### Provided services:
- `org.eclipse.edc.vault.hashicorp.client.HashicorpVaultClient`
- `org.eclipse.edc.spi.security.Vault`

##### Referenced (injected) services:
- `org.eclipse.edc.http.spi.EdcHttpClient` (required)
- `org.eclipse.edc.spi.system.ExecutorInstrumentation` (required)

#### Class: `org.eclipse.edc.vault.hashicorp.health.HashicorpVaultHealthExtension`
**Name:** "Hashicorp Vault Health"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.spi.system.health.HealthCheckService` (required)
- `org.eclipse.edc.vault.hashicorp.client.HashicorpVaultClient` (required)

Module `org.eclipse.edc:verifiable-credentials:0.9.0`
-----------------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.iam.verifiablecredentials.RevocationServiceRegistryExtension`
**Name:** "Revocation Service Extension"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
- `org.eclipse.edc.iam.verifiablecredentials.spi.model.RevocationServiceRegistry`

##### Referenced (injected) services:
_None_

Module `org.eclipse.edc:version-api:0.9.0`
------------------------------------------

_Categories: None_

### Extension points
_None_

### Extensions
#### Class: `org.eclipse.edc.connector.api.management.version.VersionApiExtension`
**Name:** "Management API: Version Information"

**Overview:** No overview provided.


##### Configuration: _None_

##### Provided services:
_None_

##### Referenced (injected) services:
- `org.eclipse.edc.web.spi.WebService` (required)
- `org.eclipse.edc.spi.types.TypeManager` (required)
- `org.eclipse.edc.spi.system.apiversion.ApiVersionService` (required)
- `org.eclipse.edc.web.spi.configuration.WebServiceConfigurer` (required)
- `org.eclipse.edc.web.spi.WebServer` (required)

Module `Web services:0.9.0`
---------------------------
_org.eclipse.edc:web-spi_

_Categories: None_

### Extension points
  - `org.eclipse.edc.web.spi.validation.InterceptorFunctionRegistry`
  - `org.eclipse.edc.web.spi.WebServer`
  - `org.eclipse.edc.web.spi.WebService`
  - `org.eclipse.edc.web.spi.configuration.WebServiceConfigurer`

### Extensions
