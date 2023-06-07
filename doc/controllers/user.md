# User

Operations about user

```ts
const userController = new UserController(client);
```

## Class Name

`UserController`

## Methods

* [Create User](../../doc/controllers/user.md#create-user)
* [Create Users With List Input](../../doc/controllers/user.md#create-users-with-list-input)
* [Login User](../../doc/controllers/user.md#login-user)
* [Logout User](../../doc/controllers/user.md#logout-user)
* [Get User by Name](../../doc/controllers/user.md#get-user-by-name)
* [Update User](../../doc/controllers/user.md#update-user)
* [Delete User](../../doc/controllers/user.md#delete-user)


# Create User

This can only be done by the logged in user.

```ts
async createUser(
  id?: bigint,
  username?: string,
  firstName?: string,
  lastName?: string,
  email?: string,
  password?: string,
  phone?: string,
  userStatus?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<User>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `bigint \| undefined` | Form, Optional | - |
| `username` | `string \| undefined` | Form, Optional | - |
| `firstName` | `string \| undefined` | Form, Optional | - |
| `lastName` | `string \| undefined` | Form, Optional | - |
| `email` | `string \| undefined` | Form, Optional | - |
| `password` | `string \| undefined` | Form, Optional | - |
| `phone` | `string \| undefined` | Form, Optional | - |
| `userStatus` | `number \| undefined` | Form, Optional | User Status |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```ts
const id = BigInt(10);

const username = 'theUser';

const firstName = 'John';

const lastName = 'James';

const email = 'john@email.com';

const password = '12345';

const phone = '12345';

const userStatus = 1;

try {
  const { result, ...httpResponse } = await userController.createUser(
    id,
    username,
    firstName,
    lastName,
    email,
    password,
    phone,
    userStatus
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Create Users With List Input

Creates list of users with given input array

```ts
async createUsersWithListInput(
  body?: User[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<User>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`User[] \| undefined`](../../doc/models/user.md) | Body, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```ts
try {
  const { result, ...httpResponse } = await userController.createUsersWithListInput();
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | successful operation | `ApiError` |


# Login User

Logs user into the system

```ts
async loginUser(
  username?: string,
  password?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string \| undefined` | Query, Optional | The user name for login |
| `password` | `string \| undefined` | Query, Optional | The password for login in clear text |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`string`

## Example Usage

```ts
try {
  const { result, ...httpResponse } = await userController.loginUser();
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username/password supplied | `ApiError` |


# Logout User

Logs out current logged in user session

```ts
async logoutUser(
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
try {
  const { result, ...httpResponse } = await userController.logoutUser();
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Get User by Name

Get user by user name

```ts
async getUserByName(
  name: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<User>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | The name that needs to be fetched. Use user1 for testing. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```ts
const name = 'name0';

try {
  const { result, ...httpResponse } = await userController.getUserByName(name);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `ApiError` |
| 404 | User not found | `ApiError` |


# Update User

This can only be done by the logged in user.

```ts
async updateUser(
  name: string,
  id?: bigint,
  username?: string,
  firstName?: string,
  lastName?: string,
  email?: string,
  password?: string,
  phone?: string,
  userStatus?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | name that need to be deleted |
| `id` | `bigint \| undefined` | Form, Optional | - |
| `username` | `string \| undefined` | Form, Optional | - |
| `firstName` | `string \| undefined` | Form, Optional | - |
| `lastName` | `string \| undefined` | Form, Optional | - |
| `email` | `string \| undefined` | Form, Optional | - |
| `password` | `string \| undefined` | Form, Optional | - |
| `phone` | `string \| undefined` | Form, Optional | - |
| `userStatus` | `number \| undefined` | Form, Optional | User Status |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const name = 'name0';

const id = BigInt(10);

const username = 'theUser';

const firstName = 'John';

const lastName = 'James';

const email = 'john@email.com';

const password = '12345';

const phone = '12345';

const userStatus = 1;

try {
  const { result, ...httpResponse } = await userController.updateUser(
    name,
    id,
    username,
    firstName,
    lastName,
    email,
    password,
    phone,
    userStatus
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Delete User

This can only be done by the logged in user.

```ts
async deleteUser(
  name: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | The name that needs to be deleted |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const name = 'name0';

try {
  const { result, ...httpResponse } = await userController.deleteUser(name);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `ApiError` |
| 404 | User not found | `ApiError` |

