# LianeAPI Class Documentation

The `LianeAPI` class is designed to interact with the Liane chatbot API, providing methods for sending questions, retrieving AI information, and constructing URLs. Below is a detailed description of the methods available in the `LianeAPI` class.

For the correct `id` and `username`, check [liaspark.chatbotcommunity.ltd](https://liaspark.chatbotcommunity.ltd). If the AI is created by an unregistered user, no need to include the `username` in the constructor.

## Constructor

### `constructor(id, username)`

**Description:** Initializes a new instance of the `LianeAPI` class.

**Parameters:**
- `id` (string): The unique identifier for the API.
- `username` (string, optional): The username associated with the API. Defaults to "unregistered".

**Usage:**
```javascript
// Example with registered user
const api = new LianeAPI("claire", "LianeAPI_Reworks");
console.log(api.id); // "claire"
console.log(api.username); // "LianeAPI_Reworks"

// Example with unregistered user
const apiUnregistered = new LianeAPI("claire");
console.log(apiUnregistered.id); // "claire"
console.log(apiUnregistered.username); // "unregistered"
```

## Methods

### `async ask(entryQuestion, key = "message")`

**Description:** Sends a question to the Liane API and returns the response.

**Parameters:**
- `entryQuestion` (string): The question to send to the API.
- `key` (string, optional): The key to retrieve from the API response. Defaults to "message".

**Returns:** 
- The value associated with the specified key in the API response.

**Usage:**
```javascript
const api = new LianeAPI("claire", "LianeAPI_Reworks");
api.ask("What is the weather today?").then(response => {
  console.log(response); // Expected response from the API
});
```

### `static async aiInfos()`

**Description:** Retrieves AI information from the API.

**Returns:** 
- The data retrieved from the API.

**Usage:**
```javascript
LianeAPI.aiInfos().then(data => {
  console.log(data); // Expected AI information from the API
});
```

### `apiUrl()`

**Description:** Constructs the URL for the API based on the instance's `id` and `username`.

**Returns:** 
- The constructed URL.

**Usage:**
```javascript
const api = new LianeAPI("claire", "LianeAPI_Reworks");
console.log(api.apiUrl()); // "https://liaspark.chatbotcommunity.ltd/@LianeAPI_Reworks/api/claire"
```

### `rawUrl(type)`

**Description:** Constructs a raw URL for the API based on the instance's `id`, `username`, and the specified type.

**Parameters:**
- `type` (string, optional): The type of raw data to request. Defaults to "botpack".

**Returns:** 
- The constructed raw URL.

**Usage:**
```javascript
const api = new LianeAPI("claire", "LianeAPI_Reworks");
console.log(api.rawUrl("data")); // "https://liaspark.chatbotcommunity.ltd/raw/LianeAPI_Reworks@claire?type=data"
```

### `static apiUrl(id, username)`

**Description:** Constructs the URL for the API based on the provided `id` and `username`.

**Parameters:**
- `id` (string): The unique identifier for the API.
- `username` (string): The username associated with the API.

**Returns:** 
- The constructed URL.

**Usage:**
```javascript
console.log(LianeAPI.apiUrl("claire", "LianeAPI_Reworks")); // "https://liaspark.chatbotcommunity.ltd/@LianeAPI_Reworks/api/claire"
```

### `async raw(type)`

**Description:** Retrieves raw data from the API based on the instance's `id`, `username`, and the specified type.

**Parameters:**
- `type` (string, optional): The type of raw data to request.

**Returns:** 
- The raw data retrieved from the API.

**Usage:**
```javascript
const api = new LianeAPI("claire", "LianeAPI_Reworks");
api.raw("data").then(data => {
  console.log(data); // Expected raw data from the API
});
```

## Summary

The `LianeAPI` class provides a structured way to interact with the Liane chatbot API. The class includes methods for sending questions, retrieving AI information, and constructing URLs. The following methods have been detailed:

1. `constructor(id, username)`
2. `async ask(entryQuestion, key = "message")`
3. `static async aiInfos()`
4. `apiUrl()`
5. `rawUrl(type)`
6. `static apiUrl(id, username)`
7. `async raw(type)`

These methods enable developers to easily integrate with the Liane chatbot API and retrieve the necessary data for their applications.