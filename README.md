
# Getting Started with Swagger Petstore - OpenAPI 3.0

## Introduction

This is a sample Pet Store Server based on the OpenAPI 3.0 specification.  You can find out more about
Swagger at [https://swagger.io](https://swagger.io). In the third iteration of the pet store, we've switched to the design first approach!
You can now help us improve the API whether it's by making changes to the definition itself or to the code.
That way, with time, we can improve the API in general, and expose some of the new features in OAS3.

_If you're looking for the Swagger 2.0/OAS 2.0 version of Petstore, then click [here](https://editor.swagger.io/?url=https://petstore.swagger.io/v2/swagger.yaml). Alternatively, you can load via the `Edit > Load Petstore OAS 2.0` menu option!_

Some useful links:

- [The Pet Store repository](https://github.com/swagger-api/swagger-petstore)
- [The source API definition for the Pet Store](https://github.com/swagger-api/swagger-petstore/blob/master/src/main/resources/openapi.yaml)

Find out more about Swagger: [http://swagger.io](http://swagger.io)

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install petstore-test-sdk@1.0.1
```

For additional package details, see the [Npm page for the petstore-test-sdk@1.0.1 npm](https://www.npmjs.com/package/petstore-test-sdk/v/1.0.1).

## Test the SDK

To validate the functionality of this SDK, you can execute all tests located in the `test` directory. This SDK utilizes `Jest` as both the testing framework and test runner.

To run the tests, navigate to the root directory of the SDK and execute the following command:

```bash
npm run test
```

Or you can also run tests with coverage report:

```bash
npm run test:coverage
```

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| timeout | `number` | Timeout for API calls.<br>*Default*: `0` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| customHeaderAuthenticationCredentials | [`CustomHeaderAuthenticationCredentials`](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/auth/custom-header-signature.md) | The credential object for customHeaderAuthentication |

The API client can be initialized as follows:

### Code-Based Client Initialization

```ts
import { Client } from 'petstore-test-sdk';

const client = new Client({
  customHeaderAuthenticationCredentials: {
    'api_key': 'api_key'
  },
  timeout: 0,
});
```

### Configuration-Based Client Initialization

```ts
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'petstore-test-sdk';

// Provide absolute path for the configuration file
const absolutePath = path.resolve('./config.json');

// Read the configuration file content
const fileContent = fs.readFileSync(absolutePath, 'utf-8');

// Initialize client from JSON configuration content
const client = Client.fromJsonConfig(fileContent);
```

See the [Configuration-Based Client Initialization](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/configuration-based-client-initialization.md) section for details.

### Environment-Based Client Initialization

```ts
import * as dotenv from 'dotenv';
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'petstore-test-sdk';

// Optional - Provide absolute path for the .env file
const absolutePath = path.resolve('./.env');

if (fs.existsSync(absolutePath)) {
  // Load environment variables from .env file
  dotenv.config({ path: absolutePath, override: true });
}

// Initialize client using environment variables
const client = Client.fromEnvironment(process.env);
```

See the [Environment-Based Client Initialization](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/environment-based-client-initialization.md) section for details.

## Authorization

This API uses the following authentication schemes.

* [`api_key (Custom Header Signature)`](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/auth/custom-header-signature.md)

## List of APIs

* [Pet](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/controllers/pet.md)
* [Store](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/controllers/store.md)
* [User](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/controllers/user.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/proxy-settings.md)
* [Configuration-Based Client Initialization](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/configuration-based-client-initialization.md)
* [Environment-Based Client Initialization](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/environment-based-client-initialization.md)

### HTTP

* [HttpRequest](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/api-response.md)
* [ApiError](https://www.github.com/sdks-io/swagger-petstore-3-js-sdk/tree/1.0.1/doc/api-error.md)

