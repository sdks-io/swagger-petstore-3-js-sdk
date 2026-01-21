# Pet

Everything about your Pets

Find out more: [http://swagger.io](http://swagger.io)

```ts
const petController = new PetController(client);
```

## Class Name

`PetController`

## Methods

* [Update Pet](../../doc/controllers/pet.md#update-pet)
* [Add Pet](../../doc/controllers/pet.md#add-pet)
* [Find Pets by Status](../../doc/controllers/pet.md#find-pets-by-status)
* [Find Pets by Tags](../../doc/controllers/pet.md#find-pets-by-tags)
* [Get Pet by Id](../../doc/controllers/pet.md#get-pet-by-id)
* [Update Pet With Form](../../doc/controllers/pet.md#update-pet-with-form)
* [Delete Pet](../../doc/controllers/pet.md#delete-pet)
* [Upload File](../../doc/controllers/pet.md#upload-file)


# Update Pet

Update an existing pet by Id

:information_source: **Note** This endpoint does not require authentication.

```ts
async updatePet(
  name: string,
  photoUrls: string[],
  id?: bigint,
  category?: Category,
  tags?: Tag[],
  petStatus?: PetStatusEnum,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Form, Required | - |
| `photoUrls` | `string[]` | Form, Required | - |
| `id` | `bigint \| undefined` | Form, Optional | - |
| `category` | [`Category \| undefined`](../../doc/models/category.md) | Form, Optional | - |
| `tags` | [`Tag[] \| undefined`](../../doc/models/tag.md) | Form, Optional | - |
| `petStatus` | [`PetStatusEnum \| undefined`](../../doc/models/pet-status-enum.md) | Form, Optional | pet status in the store |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Pet`](../../doc/models/pet.md).

## Example Usage

```ts
const name = 'doggie';

const photoUrls: string[] = [
  'photoUrls5',
  'photoUrls6',
  'photoUrls7'
];

const id = BigInt(10);

const category: Category = {
  id: BigInt(1),
  name: 'Dogs',
};

const tags: Tag[] = [
  {
  }
];

try {
  const response = await petController.updatePet(
    name,
    photoUrls,
    id,
    category,
    tags
  );

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
  }
}
```

## Example Response *(as JSON)*

```json
{
  "name": "Rex",
  "photoUrls": [
    "https://example.com/photo1.jpg",
    "https://example.com/photo2.jpg"
  ],
  "id": 123,
  "category": {
    "id": 1,
    "name": "Dogs"
  },
  "tags": [
    {
      "id": 1,
      "name": "friendly"
    },
    {
      "id": 2,
      "name": "playful"
    }
  ],
  "petStatus": "available"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `ApiError` |
| 404 | Pet not found | `ApiError` |
| 405 | Validation exception | `ApiError` |


# Add Pet

Add a new pet to the store

:information_source: **Note** This endpoint does not require authentication.

```ts
async addPet(
  name: string,
  photoUrls: string[],
  id?: bigint,
  category?: Category,
  tags?: Tag[],
  petStatus?: PetStatusEnum,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Form, Required | - |
| `photoUrls` | `string[]` | Form, Required | - |
| `id` | `bigint \| undefined` | Form, Optional | - |
| `category` | [`Category \| undefined`](../../doc/models/category.md) | Form, Optional | - |
| `tags` | [`Tag[] \| undefined`](../../doc/models/tag.md) | Form, Optional | - |
| `petStatus` | [`PetStatusEnum \| undefined`](../../doc/models/pet-status-enum.md) | Form, Optional | pet status in the store |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Pet`](../../doc/models/pet.md).

## Example Usage

```ts
const name = 'doggie';

const photoUrls: string[] = [
  'https://example.com/photo2.jpg'
];

const id = BigInt(10);

const category: Category = {
  id: BigInt(232),
  name: 'name2',
};

const tags: Tag[] = [
  {
    id: BigInt(26),
    name: 'name0',
  }
];

const petStatus = PetStatusEnum.Sold;

try {
  const response = await petController.addPet(
    name,
    photoUrls,
    id,
    category,
    tags,
    petStatus
  );

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
  }
}
```

## Example Response *(as JSON)*

```json
{
  "name": "Rex",
  "photoUrls": [
    "https://example.com/photo1.jpg",
    "https://example.com/photo2.jpg"
  ],
  "id": 123,
  "category": {
    "id": 1,
    "name": "Dogs"
  },
  "tags": [
    {
      "id": 1,
      "name": "friendly"
    },
    {
      "id": 2,
      "name": "playful"
    }
  ],
  "petStatus": "available"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 405 | Invalid input | `ApiError` |


# Find Pets by Status

Multiple status values can be provided with comma separated strings

:information_source: **Note** This endpoint does not require authentication.

```ts
async findPetsByStatus(
  status?: StatusEnum,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet[]>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | [`StatusEnum \| undefined`](../../doc/models/status-enum.md) | Query, Optional | Status values that need to be considered for filter<br><br>**Default**: `StatusEnum.Available` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Pet[]`](../../doc/models/pet.md).

## Example Usage

```ts
const status = StatusEnum.Available;

try {
  const response = await petController.findPetsByStatus(status);

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
  }
}
```

## Example Response *(as JSON)*

```json
[
  {
    "id": 10,
    "name": "doggie",
    "photoUrls": [
      "photoUrls5",
      "photoUrls6"
    ],
    "category": {
      "id": 232,
      "name": "name2"
    },
    "tags": [
      {
        "id": 26,
        "name": "name0"
      }
    ],
    "petStatus": "sold"
  },
  {
    "id": 11,
    "name": "kitty",
    "photoUrls": [
      "photoUrls7",
      "photoUrls8"
    ],
    "category": {
      "id": 233,
      "name": "name3"
    },
    "tags": [
      {
        "id": 27,
        "name": "name1"
      }
    ],
    "petStatus": "available"
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid status value | `ApiError` |


# Find Pets by Tags

Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

:information_source: **Note** This endpoint does not require authentication.

```ts
async findPetsByTags(
  tags?: string[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet[]>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tags` | `string[] \| undefined` | Query, Optional | Tags to filter by |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Pet[]`](../../doc/models/pet.md).

## Example Usage

```ts
try {
  const response = await petController.findPetsByTags();

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
  }
}
```

## Example Response *(as JSON)*

```json
[
  {
    "id": 10,
    "name": "doggie",
    "photoUrls": [
      "photoUrls5",
      "photoUrls6"
    ],
    "category": {
      "id": 232,
      "name": "name2"
    },
    "tags": [
      {
        "id": 26,
        "name": "name0"
      }
    ],
    "petStatus": "sold"
  },
  {
    "id": 11,
    "name": "kitty",
    "photoUrls": [
      "photoUrls7",
      "photoUrls8"
    ],
    "category": {
      "id": 233,
      "name": "name3"
    },
    "tags": [
      {
        "id": 27,
        "name": "name1"
      }
    ],
    "petStatus": "available"
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid tag value | `ApiError` |


# Get Pet by Id

Returns a single pet

```ts
async getPetById(
  petId: bigint,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | ID of pet to return |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Pet`](../../doc/models/pet.md).

## Example Usage

```ts
const petId = BigInt(152);

try {
  const response = await petController.getPetById(petId);

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
  }
}
```

## Example Response *(as JSON)*

```json
{
  "name": "Rex",
  "photoUrls": [
    "https://example.com/photo1.jpg",
    "https://example.com/photo2.jpg"
  ],
  "id": 123,
  "category": {
    "id": 1,
    "name": "Dogs"
  },
  "tags": [
    {
      "id": 1,
      "name": "friendly"
    },
    {
      "id": 2,
      "name": "playful"
    }
  ],
  "petStatus": "available"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `ApiError` |
| 404 | Pet not found | `ApiError` |


# Update Pet With Form

:information_source: **Note** This endpoint does not require authentication.

```ts
async updatePetWithForm(
  petId: bigint,
  name?: string,
  status?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | ID of pet that needs to be updated |
| `name` | `string \| undefined` | Query, Optional | Name of pet that needs to be updated |
| `status` | `string \| undefined` | Query, Optional | Status of pet that needs to be updated |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const petId = BigInt(152);

try {
  const response = await petController.updatePetWithForm(petId);

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 405 | Invalid input | `ApiError` |


# Delete Pet

delete a pet

:information_source: **Note** This endpoint does not require authentication.

```ts
async deletePet(
  petId: bigint,
  apiKey?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | Pet id to delete |
| `apiKey` | `string \| undefined` | Header, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const petId = BigInt(152);

try {
  const response = await petController.deletePet(petId);

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid pet value | `ApiError` |


# Upload File

:information_source: **Note** This endpoint does not require authentication.

```ts
async uploadFile(
  petId: bigint,
  additionalMetadata?: string,
  body?: FileWrapper,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PetImage>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | ID of pet to update |
| `additionalMetadata` | `string \| undefined` | Query, Optional | Additional Metadata |
| `body` | `FileWrapper \| undefined` | Form, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PetImage`](../../doc/models/pet-image.md).

## Example Usage

```ts
const petId = BigInt(152);

try {
  const response = await petController.uploadFile(petId);

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
  }
}
```

## Example Response *(as JSON)*

```json
{
  "code": 200,
  "type": "unknown",
  "message": "additionalMetadata"
}
```

