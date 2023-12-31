---
title: Api Gateway v8.65.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="api-gateway">Api Gateway v8.65.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Daytona Api Gateway REST API

<h1 id="api-gateway-workspace">Workspace</h1>

## createWorkspace

<a id="opIdcreateWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /workspace \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /workspace HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "clusterId": "string",
  "createdFromTemplate": true,
  "gitRepositoryUrl": "string",
  "teamId": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/workspace',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '/workspace',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/workspace', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/workspace', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/workspace", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /workspace`

> Body parameter

```json
{
  "clusterId": "string",
  "createdFromTemplate": true,
  "gitRepositoryUrl": "string",
  "teamId": "string"
}
```

<h3 id="createworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[WorkspaceFromGitRepositoryUrlCreation](#schemaworkspacefromgitrepositoryurlcreation)|false|none|

> Example responses

> 200 Response

```json
{
  "createdAt": "2019-08-24T14:15:22Z",
  "createdFromTemplate": true,
  "destroyed": true,
  "error": "string",
  "errorLog": "string",
  "gitContext": {
    "branch": "string",
    "cloneUrl": "string",
    "hasDevContainerConfig": true,
    "owner": "string",
    "path": "string",
    "prNumber": 0,
    "providerId": "string",
    "repo": "string",
    "sha": "string",
    "source": "string",
    "webUrl": "string"
  },
  "gitStatus": {
    "ahead": 0,
    "behind": 0,
    "current": "string",
    "detached": true,
    "files": [
      {
        "from": "string",
        "index": "string",
        "path": "string",
        "workingDir": "string"
      }
    ],
    "tracking": "string"
  },
  "id": "string",
  "pinned": true,
  "shared": true,
  "sshAccessToken": "string",
  "teamId": "string",
  "updatedAt": "2019-08-24T14:15:22Z",
  "userId": "string",
  "version": 0,
  "workspaceInstance": {
    "className": "kata",
    "clusterId": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "error": "string",
    "errorLog": "string",
    "id": "string",
    "lastKeepAliveSignal": "2019-08-24T14:15:22Z",
    "startedAt": "2019-08-24T14:15:22Z",
    "state": "none",
    "stoppedAt": "2019-08-24T14:15:22Z",
    "token": "string",
    "updatedAt": "2019-08-24T14:15:22Z",
    "version": 0,
    "workspaceId": "string"
  }
}
```

<h3 id="createworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Workspace](#schemaworkspace)|

<aside class="success">
This operation does not require authentication
</aside>

## getWorkspaceList

<a id="opIdgetWorkspaceList"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /workspace?teamId=string \
  -H 'Accept: application/json'

```

```http
GET /workspace?teamId=string HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/workspace?teamId=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/workspace',
  params: {
  'teamId' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/workspace', params={
  'teamId': 'string'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/workspace', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace?teamId=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/workspace", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /workspace`

<h3 id="getworkspacelist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|teamId|query|string|true|none|
|workspaceId|query|string|false|none|
|limit|query|number|false|none|
|offset|query|number|false|none|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "createdAt": "2019-08-24T14:15:22Z",
      "createdFromTemplate": true,
      "destroyed": true,
      "error": "string",
      "errorLog": "string",
      "gitContext": {
        "branch": "string",
        "cloneUrl": "string",
        "hasDevContainerConfig": true,
        "owner": "string",
        "path": "string",
        "prNumber": 0,
        "providerId": "string",
        "repo": "string",
        "sha": "string",
        "source": "string",
        "webUrl": "string"
      },
      "gitStatus": {
        "ahead": 0,
        "behind": 0,
        "current": "string",
        "detached": true,
        "files": [
          {
            "from": "string",
            "index": "string",
            "path": "string",
            "workingDir": "string"
          }
        ],
        "tracking": "string"
      },
      "id": "string",
      "pinned": true,
      "shared": true,
      "sshAccessToken": "string",
      "teamId": "string",
      "updatedAt": "2019-08-24T14:15:22Z",
      "userId": "string",
      "version": 0,
      "workspaceInstance": {
        "className": "kata",
        "clusterId": "string",
        "createdAt": "2019-08-24T14:15:22Z",
        "error": "string",
        "errorLog": "string",
        "id": "string",
        "lastKeepAliveSignal": "2019-08-24T14:15:22Z",
        "startedAt": "2019-08-24T14:15:22Z",
        "state": "none",
        "stoppedAt": "2019-08-24T14:15:22Z",
        "token": "string",
        "updatedAt": "2019-08-24T14:15:22Z",
        "version": 0,
        "workspaceId": "string"
      }
    }
  ],
  "total": 0
}
```

<h3 id="getworkspacelist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[WorkspaceList](#schemaworkspacelist)|

<aside class="success">
This operation does not require authentication
</aside>

## destroyWorkspace

<a id="opIddestroyWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /workspace/{id}/destroy \
  -H 'Accept: application/json'

```

```http
DELETE /workspace/{id}/destroy HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/workspace/{id}/destroy',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete '/workspace/{id}/destroy',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/workspace/{id}/destroy', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/workspace/{id}/destroy', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace/{id}/destroy");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/workspace/{id}/destroy", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /workspace/{id}/destroy`

<h3 id="destroyworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "createdAt": "2019-08-24T14:15:22Z",
  "createdFromTemplate": true,
  "destroyed": true,
  "error": "string",
  "errorLog": "string",
  "gitContext": {
    "branch": "string",
    "cloneUrl": "string",
    "hasDevContainerConfig": true,
    "owner": "string",
    "path": "string",
    "prNumber": 0,
    "providerId": "string",
    "repo": "string",
    "sha": "string",
    "source": "string",
    "webUrl": "string"
  },
  "gitStatus": {
    "ahead": 0,
    "behind": 0,
    "current": "string",
    "detached": true,
    "files": [
      {
        "from": "string",
        "index": "string",
        "path": "string",
        "workingDir": "string"
      }
    ],
    "tracking": "string"
  },
  "id": "string",
  "pinned": true,
  "shared": true,
  "sshAccessToken": "string",
  "teamId": "string",
  "updatedAt": "2019-08-24T14:15:22Z",
  "userId": "string",
  "version": 0,
  "workspaceInstance": {
    "className": "kata",
    "clusterId": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "error": "string",
    "errorLog": "string",
    "id": "string",
    "lastKeepAliveSignal": "2019-08-24T14:15:22Z",
    "startedAt": "2019-08-24T14:15:22Z",
    "state": "none",
    "stoppedAt": "2019-08-24T14:15:22Z",
    "token": "string",
    "updatedAt": "2019-08-24T14:15:22Z",
    "version": 0,
    "workspaceId": "string"
  }
}
```

<h3 id="destroyworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Workspace](#schemaworkspace)|

<aside class="success">
This operation does not require authentication
</aside>

## getWorkspace

<a id="opIdgetWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /workspace/{id} \
  -H 'Accept: application/json'

```

```http
GET /workspace/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/workspace/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/workspace/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/workspace/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/workspace/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/workspace/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /workspace/{id}`

<h3 id="getworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "createdAt": "2019-08-24T14:15:22Z",
  "createdFromTemplate": true,
  "destroyed": true,
  "error": "string",
  "errorLog": "string",
  "gitContext": {
    "branch": "string",
    "cloneUrl": "string",
    "hasDevContainerConfig": true,
    "owner": "string",
    "path": "string",
    "prNumber": 0,
    "providerId": "string",
    "repo": "string",
    "sha": "string",
    "source": "string",
    "webUrl": "string"
  },
  "gitStatus": {
    "ahead": 0,
    "behind": 0,
    "current": "string",
    "detached": true,
    "files": [
      {
        "from": "string",
        "index": "string",
        "path": "string",
        "workingDir": "string"
      }
    ],
    "tracking": "string"
  },
  "id": "string",
  "pinned": true,
  "shared": true,
  "sshAccessToken": "string",
  "teamId": "string",
  "updatedAt": "2019-08-24T14:15:22Z",
  "userId": "string",
  "version": 0,
  "workspaceInstance": {
    "className": "kata",
    "clusterId": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "error": "string",
    "errorLog": "string",
    "id": "string",
    "lastKeepAliveSignal": "2019-08-24T14:15:22Z",
    "startedAt": "2019-08-24T14:15:22Z",
    "state": "none",
    "stoppedAt": "2019-08-24T14:15:22Z",
    "token": "string",
    "updatedAt": "2019-08-24T14:15:22Z",
    "version": 0,
    "workspaceId": "string"
  }
}
```

<h3 id="getworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Workspace](#schemaworkspace)|

<aside class="success">
This operation does not require authentication
</aside>

## isWorkspaceShared

<a id="opIdisWorkspaceShared"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /workspace/{id}/shared \
  -H 'Accept: */*'

```

```http
GET /workspace/{id}/shared HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/workspace/{id}/shared',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get '/workspace/{id}/shared',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('/workspace/{id}/shared', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/workspace/{id}/shared', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace/{id}/shared");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/workspace/{id}/shared", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /workspace/{id}/shared`

<h3 id="isworkspaceshared-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="isworkspaceshared-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="isworkspaceshared-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## pinWorkspace

<a id="opIdpinWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /workspace/{id}/pin \
  -H 'Accept: */*'

```

```http
POST /workspace/{id}/pin HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/workspace/{id}/pin',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/workspace/{id}/pin',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/workspace/{id}/pin', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/workspace/{id}/pin', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace/{id}/pin");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/workspace/{id}/pin", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /workspace/{id}/pin`

<h3 id="pinworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="pinworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="pinworkspace-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## shareWorkspace

<a id="opIdshareWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /workspace/{id}/share \
  -H 'Accept: */*'

```

```http
POST /workspace/{id}/share HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/workspace/{id}/share',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/workspace/{id}/share',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/workspace/{id}/share', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/workspace/{id}/share', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace/{id}/share");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/workspace/{id}/share", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /workspace/{id}/share`

<h3 id="shareworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="shareworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="shareworkspace-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## unpinWorkspace

<a id="opIdunpinWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /workspace/{id}/unpin \
  -H 'Accept: */*'

```

```http
POST /workspace/{id}/unpin HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/workspace/{id}/unpin',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/workspace/{id}/unpin',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/workspace/{id}/unpin', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/workspace/{id}/unpin', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace/{id}/unpin");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/workspace/{id}/unpin", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /workspace/{id}/unpin`

<h3 id="unpinworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="unpinworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="unpinworkspace-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## unshareWorkspace

<a id="opIdunshareWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /workspace/{id}/unshare \
  -H 'Accept: */*'

```

```http
POST /workspace/{id}/unshare HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/workspace/{id}/unshare',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/workspace/{id}/unshare',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/workspace/{id}/unshare', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/workspace/{id}/unshare', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace/{id}/unshare");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/workspace/{id}/unshare", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /workspace/{id}/unshare`

<h3 id="unshareworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="unshareworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="unshareworkspace-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-gateway-user">User</h1>

## createUserEnvironmentVariable

<a id="opIdcreateUserEnvironmentVariable"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /user/environment-variables \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST /user/environment-variables HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "name": "string",
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/user/environment-variables',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post '/user/environment-variables',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('/user/environment-variables', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/user/environment-variables', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/environment-variables");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/user/environment-variables", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /user/environment-variables`

> Body parameter

```json
{
  "name": "string",
  "value": "string"
}
```

<h3 id="createuserenvironmentvariable-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[EnvironmentVariableCreation](#schemaenvironmentvariablecreation)|false|none|

> Example responses

> 201 Response

<h3 id="createuserenvironmentvariable-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|Inline|

<h3 id="createuserenvironmentvariable-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## getUserEnvironmentVariableList

<a id="opIdgetUserEnvironmentVariableList"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /user/environment-variables \
  -H 'Accept: application/json'

```

```http
GET /user/environment-variables HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/user/environment-variables',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/user/environment-variables',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/user/environment-variables', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/user/environment-variables', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/environment-variables");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/user/environment-variables", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/environment-variables`

> Example responses

> 200 Response

```json
[
  {
    "name": "string",
    "value": "string"
  }
]
```

<h3 id="getuserenvironmentvariablelist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getuserenvironmentvariablelist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[EnvironmentVariable](#schemaenvironmentvariable)]|false|none|none|
|» name|string|true|none|Name|
|» value|string|true|none|Value|

<aside class="success">
This operation does not require authentication
</aside>

## createUserSSHKey

<a id="opIdcreateUserSSHKey"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /user/ssh-keys \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST /user/ssh-keys HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "expiresAt": "2019-08-24T14:15:22Z",
  "name": "My SSH key",
  "publicKey": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/user/ssh-keys',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post '/user/ssh-keys',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('/user/ssh-keys', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/user/ssh-keys', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/ssh-keys");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/user/ssh-keys", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /user/ssh-keys`

> Body parameter

```json
{
  "expiresAt": "2019-08-24T14:15:22Z",
  "name": "My SSH key",
  "publicKey": "string"
}
```

<h3 id="createusersshkey-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PublicSSHKeyCreation](#schemapublicsshkeycreation)|false|none|

> Example responses

> 201 Response

<h3 id="createusersshkey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|Inline|

<h3 id="createusersshkey-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## getUserSSHKeys

<a id="opIdgetUserSSHKeys"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /user/ssh-keys \
  -H 'Accept: application/json'

```

```http
GET /user/ssh-keys HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/user/ssh-keys',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/user/ssh-keys',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/user/ssh-keys', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/user/ssh-keys', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/ssh-keys");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/user/ssh-keys", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/ssh-keys`

> Example responses

> 200 Response

```json
[
  {
    "addedAt": "2019-08-24T14:15:22Z",
    "expiresAt": "2019-08-24T14:15:22Z",
    "id": "string",
    "name": "My SSH key"
  }
]
```

<h3 id="getusersshkeys-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getusersshkeys-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[PublicSSHKey](#schemapublicsshkey)]|false|none|none|
|» addedAt|string(date-time)|true|none|Added at|
|» expiresAt|string(date-time)|false|none|Expires at|
|» id|string|true|none|Id|
|» name|string|true|none|SSH key name|

<aside class="success">
This operation does not require authentication
</aside>

## deleteUser

<a id="opIddeleteUser"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /user

```

```http
DELETE /user HTTP/1.1

```

```javascript

fetch('/user',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.delete '/user',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/user')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/user', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/user", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /user`

<h3 id="deleteuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|

<aside class="success">
This operation does not require authentication
</aside>

## getUser

<a id="opIdgetUser"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /user \
  -H 'Accept: application/json'

```

```http
GET /user HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/user',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/user',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/user', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/user', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/user", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user`

> Example responses

> 200 Response

```json
{
  "avatarUrl": "string",
  "disabled": true,
  "id": "string",
  "markedForDeletion": true,
  "preferences": {
    "defaultIde": "browser",
    "dotfilesRepositoryUrl": "string"
  },
  "primaryEmail": "string",
  "publicSSHKey": "string",
  "username": "string"
}
```

<h3 id="getuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[User](#schemauser)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteUserEnvironmentVariable

<a id="opIddeleteUserEnvironmentVariable"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /user/environment-variables/{name}

```

```http
DELETE /user/environment-variables/{name} HTTP/1.1

```

```javascript

fetch('/user/environment-variables/{name}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.delete '/user/environment-variables/{name}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/user/environment-variables/{name}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/user/environment-variables/{name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/environment-variables/{name}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/user/environment-variables/{name}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /user/environment-variables/{name}`

<h3 id="deleteuserenvironmentvariable-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|name|path|string|true|none|

<h3 id="deleteuserenvironmentvariable-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|

<aside class="success">
This operation does not require authentication
</aside>

## updateUserEnvironmentVariable

<a id="opIdupdateUserEnvironmentVariable"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /user/environment-variables/{name} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT /user/environment-variables/{name} HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "name": "string",
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/user/environment-variables/{name}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.put '/user/environment-variables/{name}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('/user/environment-variables/{name}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/user/environment-variables/{name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/environment-variables/{name}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/user/environment-variables/{name}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /user/environment-variables/{name}`

> Body parameter

```json
{
  "name": "string",
  "value": "string"
}
```

<h3 id="updateuserenvironmentvariable-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|name|path|string|true|none|
|body|body|[EnvironmentVariableUpdate](#schemaenvironmentvariableupdate)|false|none|

> Example responses

> 200 Response

<h3 id="updateuserenvironmentvariable-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="updateuserenvironmentvariable-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## deleteUserSSHKey

<a id="opIddeleteUserSSHKey"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /user/ssh-keys/{id}

```

```http
DELETE /user/ssh-keys/{id} HTTP/1.1

```

```javascript

fetch('/user/ssh-keys/{id}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.delete '/user/ssh-keys/{id}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/user/ssh-keys/{id}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/user/ssh-keys/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/ssh-keys/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/user/ssh-keys/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /user/ssh-keys/{id}`

<h3 id="deleteusersshkey-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

<h3 id="deleteusersshkey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|

<aside class="success">
This operation does not require authentication
</aside>

## getPublicSSHKey

<a id="opIdgetPublicSSHKey"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /user/public-key \
  -H 'Accept: */*'

```

```http
GET /user/public-key HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/user/public-key',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get '/user/public-key',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('/user/public-key', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/user/public-key', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/public-key");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/user/public-key", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/public-key`

> Example responses

> 200 Response

<h3 id="getpublicsshkey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Public Key|string|

<aside class="success">
This operation does not require authentication
</aside>

## getUserGitNamespaces

<a id="opIdgetUserGitNamespaces"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /user/git-namespaces/{provider} \
  -H 'Accept: application/json'

```

```http
GET /user/git-namespaces/{provider} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/user/git-namespaces/{provider}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/user/git-namespaces/{provider}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/user/git-namespaces/{provider}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/user/git-namespaces/{provider}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/git-namespaces/{provider}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/user/git-namespaces/{provider}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/git-namespaces/{provider}`

<h3 id="getusergitnamespaces-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|provider|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "personal": true,
    "provider": "string"
  }
]
```

<h3 id="getusergitnamespaces-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getusergitnamespaces-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[GitNamespace](#schemagitnamespace)]|false|none|none|
|» id|string|true|none|none|
|» name|string|true|none|none|
|» personal|boolean|false|none|none|
|» provider|string|true|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## getUserGitRepos

<a id="opIdgetUserGitRepos"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /user/git-repos/{provider}/{namespaceId} \
  -H 'Accept: application/json'

```

```http
GET /user/git-repos/{provider}/{namespaceId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/user/git-repos/{provider}/{namespaceId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/user/git-repos/{provider}/{namespaceId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/user/git-repos/{provider}/{namespaceId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/user/git-repos/{provider}/{namespaceId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/git-repos/{provider}/{namespaceId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/user/git-repos/{provider}/{namespaceId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/git-repos/{provider}/{namespaceId}`

<h3 id="getusergitrepos-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|provider|path|string|true|none|
|namespaceId|path|string|true|none|
|personal|query|boolean|false|none|
|offset|query|number|false|none|
|limit|query|number|false|none|
|query|query|string|false|none|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "fullName": "string",
      "htmlUrl": "string",
      "name": "string"
    }
  ],
  "total": 0
}
```

<h3 id="getusergitrepos-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[GitRepositoryList](#schemagitrepositorylist)|

<aside class="success">
This operation does not require authentication
</aside>

## updateUserDefaultIde

<a id="opIdupdateUserDefaultIde"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /user/default-ide \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT /user/default-ide HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "defaultIde": "browser"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/user/default-ide',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.put '/user/default-ide',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('/user/default-ide', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/user/default-ide', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/default-ide");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/user/default-ide", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /user/default-ide`

> Body parameter

```json
{
  "defaultIde": "browser"
}
```

<h3 id="updateuserdefaultide-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserUpdateDefaultIde](#schemauserupdatedefaultide)|false|none|

> Example responses

> 200 Response

<h3 id="updateuserdefaultide-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="updateuserdefaultide-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## updateUserDotfilesRepositoryUrl

<a id="opIdupdateUserDotfilesRepositoryUrl"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /user/dotfiles-repository \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT /user/dotfiles-repository HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "dotfilesRepositoryUrl": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/user/dotfiles-repository',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.put '/user/dotfiles-repository',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('/user/dotfiles-repository', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/user/dotfiles-repository', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/user/dotfiles-repository");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/user/dotfiles-repository", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /user/dotfiles-repository`

> Body parameter

```json
{
  "dotfilesRepositoryUrl": "string"
}
```

<h3 id="updateuserdotfilesrepositoryurl-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserUpdateDotfilesRepositoryUrl](#schemauserupdatedotfilesrepositoryurl)|false|none|

> Example responses

> 200 Response

<h3 id="updateuserdotfilesrepositoryurl-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="updateuserdotfilesrepositoryurl-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-gateway-team">Team</h1>

## acceptTeamInvitation

<a id="opIdacceptTeamInvitation"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /team/{id}/invite/accept/{invitationId} \
  -H 'Accept: */*'

```

```http
POST /team/{id}/invite/accept/{invitationId} HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/team/{id}/invite/accept/{invitationId}',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/team/{id}/invite/accept/{invitationId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/team/{id}/invite/accept/{invitationId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/team/{id}/invite/accept/{invitationId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/invite/accept/{invitationId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/team/{id}/invite/accept/{invitationId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /team/{id}/invite/accept/{invitationId}`

<h3 id="acceptteaminvitation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|invitationId|path|string|true|none|

> Example responses

> 200 Response

<h3 id="acceptteaminvitation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="acceptteaminvitation-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## createTeam

<a id="opIdcreateTeam"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /team \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /team HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "name": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/team',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '/team',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/team', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/team', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/team", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /team`

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="createteam-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TeamCreation](#schemateamcreation)|false|none|

> Example responses

> 200 Response

```json
{
  "hasActiveSubscription": true,
  "id": "string",
  "name": "string",
  "privateMembers": true
}
```

<h3 id="createteam-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Team](#schemateam)|

<aside class="success">
This operation does not require authentication
</aside>

## getTeams

<a id="opIdgetTeams"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /team \
  -H 'Accept: application/json'

```

```http
GET /team HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/team',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/team',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/team', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/team', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/team", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /team`

<h3 id="getteams-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|role|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|role|owner|
|role|admin|
|role|member|

> Example responses

> 200 Response

```json
[
  {
    "hasActiveSubscription": true,
    "id": "string",
    "name": "string",
    "privateMembers": true
  }
]
```

<h3 id="getteams-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getteams-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Team](#schemateam)]|false|none|none|
|» hasActiveSubscription|boolean|true|none|Team has active subscription|
|» id|string|true|none|none|
|» name|string|true|none|Name|
|» privateMembers|boolean|true|none|Private members|

<aside class="success">
This operation does not require authentication
</aside>

## createTeamInvitation

<a id="opIdcreateTeamInvitation"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /team/{id}/invitation \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST /team/{id}/invitation HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "email": "user@example.com",
  "expiresAt": "2019-08-24T14:15:22Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/team/{id}/invitation',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post '/team/{id}/invitation',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('/team/{id}/invitation', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/team/{id}/invitation', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/invitation");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/team/{id}/invitation", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /team/{id}/invitation`

> Body parameter

```json
{
  "email": "user@example.com",
  "expiresAt": "2019-08-24T14:15:22Z"
}
```

<h3 id="createteaminvitation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[TeamInvitationCreation](#schemateaminvitationcreation)|true|none|

> Example responses

> 201 Response

<h3 id="createteaminvitation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|Inline|

<h3 id="createteaminvitation-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## getTeamInvitations

<a id="opIdgetTeamInvitations"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /team/{id}/invitation \
  -H 'Accept: application/json'

```

```http
GET /team/{id}/invitation HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/team/{id}/invitation',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/team/{id}/invitation',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/team/{id}/invitation', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/team/{id}/invitation', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/invitation");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/team/{id}/invitation", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /team/{id}/invitation`

<h3 id="getteaminvitations-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "email": "user@example.com",
    "expiresAt": "2019-08-24T14:15:22Z",
    "id": "string"
  }
]
```

<h3 id="getteaminvitations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getteaminvitations-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[TeamInvitation](#schemateaminvitation)]|false|none|none|
|» email|string(email)|true|none|none|
|» expiresAt|string(date-time)|true|none|none|
|» id|string|true|none|Invitation Id|

<aside class="success">
This operation does not require authentication
</aside>

## createTeamSubscription

<a id="opIdcreateTeamSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /team/{id}/subscriptions \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST /team/{id}/subscriptions HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "disabled": false,
  "end": "2019-08-24T14:15:22Z",
  "id": "string",
  "planId": "string",
  "seats": 0,
  "start": "2019-08-24T14:15:22Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/team/{id}/subscriptions',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post '/team/{id}/subscriptions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('/team/{id}/subscriptions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/team/{id}/subscriptions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/subscriptions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/team/{id}/subscriptions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /team/{id}/subscriptions`

> Body parameter

```json
{
  "disabled": false,
  "end": "2019-08-24T14:15:22Z",
  "id": "string",
  "planId": "string",
  "seats": 0,
  "start": "2019-08-24T14:15:22Z"
}
```

<h3 id="createteamsubscription-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[SubscriptionCreation](#schemasubscriptioncreation)|false|none|

> Example responses

> 201 Response

<h3 id="createteamsubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|Inline|

<h3 id="createteamsubscription-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## getTeamSubscriptionList

<a id="opIdgetTeamSubscriptionList"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /team/{id}/subscriptions \
  -H 'Accept: application/json'

```

```http
GET /team/{id}/subscriptions HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/team/{id}/subscriptions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/team/{id}/subscriptions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/team/{id}/subscriptions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/team/{id}/subscriptions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/subscriptions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/team/{id}/subscriptions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /team/{id}/subscriptions`

<h3 id="getteamsubscriptionlist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "disabled": true,
    "end": "2019-08-24T14:15:22Z",
    "id": "string",
    "plan": {
      "buildCredits": 0,
      "credits": 0,
      "id": "string",
      "inactivityTimeoutInMinutes": 0,
      "name": "string",
      "parallelBuilds": 0,
      "parallelWorkspaces": 0,
      "pinnedWorkspaces": 0
    },
    "seats": 0,
    "start": "2019-08-24T14:15:22Z",
    "teamId": "string"
  }
]
```

<h3 id="getteamsubscriptionlist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getteamsubscriptionlist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Subscription](#schemasubscription)]|false|none|none|
|» disabled|boolean|true|none|Disabled|
|» end|string(date-time)|false|none|End|
|» id|string|true|none|none|
|» plan|[Plan](#schemaplan)|true|none|none|
|»» buildCredits|number|true|none|Build credits|
|»» credits|number|true|none|Workspace credits|
|»» id|string|true|none|none|
|»» inactivityTimeoutInMinutes|number|true|none|Inactivity timeout in minutes|
|»» name|string|true|none|Name|
|»» parallelBuilds|number|true|none|Parallel builds|
|»» parallelWorkspaces|number|true|none|Parallel workspaces|
|»» pinnedWorkspaces|number|true|none|Limit of pinned workspaces|
|» seats|number|true|none|Max team members|
|» start|string(date-time)|true|none|Start|
|» teamId|string|true|none|Team id|

<aside class="success">
This operation does not require authentication
</aside>

## deleteTeam

<a id="opIddeleteTeam"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /team/{id}

```

```http
DELETE /team/{id} HTTP/1.1

```

```javascript

fetch('/team/{id}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.delete '/team/{id}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/team/{id}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/team/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/team/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /team/{id}`

<h3 id="deleteteam-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

<h3 id="deleteteam-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTeam

<a id="opIdgetTeam"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /team/{id} \
  -H 'Accept: application/json'

```

```http
GET /team/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/team/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/team/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/team/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/team/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/team/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /team/{id}`

<h3 id="getteam-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "hasActiveSubscription": true,
  "id": "string",
  "name": "string",
  "privateMembers": true
}
```

<h3 id="getteam-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Team](#schemateam)|

<aside class="success">
This operation does not require authentication
</aside>

## updateTeam

<a id="opIdupdateTeam"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /team/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PATCH /team/{id} HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "name": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/team/{id}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.patch '/team/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.patch('/team/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/team/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/team/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /team/{id}`

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="updateteam-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[TeamUpdate](#schemateamupdate)|true|none|

> Example responses

> 200 Response

<h3 id="updateteam-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="updateteam-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## disableTeamSubscription

<a id="opIddisableTeamSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /team/{id}/subscriptions/{subscriptionId}/disable \
  -H 'Accept: */*'

```

```http
POST /team/{id}/subscriptions/{subscriptionId}/disable HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/team/{id}/subscriptions/{subscriptionId}/disable',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/team/{id}/subscriptions/{subscriptionId}/disable',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/team/{id}/subscriptions/{subscriptionId}/disable', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/team/{id}/subscriptions/{subscriptionId}/disable', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/subscriptions/{subscriptionId}/disable");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/team/{id}/subscriptions/{subscriptionId}/disable", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /team/{id}/subscriptions/{subscriptionId}/disable`

<h3 id="disableteamsubscription-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|subscriptionId|path|string|true|none|

> Example responses

> 200 Response

<h3 id="disableteamsubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="disableteamsubscription-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## enableTeamSubscription

<a id="opIdenableTeamSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /team/{id}/subscriptions/{subscriptionId}/enable \
  -H 'Accept: */*'

```

```http
POST /team/{id}/subscriptions/{subscriptionId}/enable HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/team/{id}/subscriptions/{subscriptionId}/enable',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/team/{id}/subscriptions/{subscriptionId}/enable',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/team/{id}/subscriptions/{subscriptionId}/enable', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/team/{id}/subscriptions/{subscriptionId}/enable', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/subscriptions/{subscriptionId}/enable");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/team/{id}/subscriptions/{subscriptionId}/enable", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /team/{id}/subscriptions/{subscriptionId}/enable`

<h3 id="enableteamsubscription-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|subscriptionId|path|string|true|none|

> Example responses

> 200 Response

<h3 id="enableteamsubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="enableteamsubscription-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## getActiveTeamSubscription

<a id="opIdgetActiveTeamSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /team/{id}/subscriptions/active \
  -H 'Accept: application/json'

```

```http
GET /team/{id}/subscriptions/active HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/team/{id}/subscriptions/active',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/team/{id}/subscriptions/active',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/team/{id}/subscriptions/active', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/team/{id}/subscriptions/active', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/subscriptions/active");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/team/{id}/subscriptions/active", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /team/{id}/subscriptions/active`

<h3 id="getactiveteamsubscription-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "disabled": true,
  "end": "2019-08-24T14:15:22Z",
  "id": "string",
  "plan": {
    "buildCredits": 0,
    "credits": 0,
    "id": "string",
    "inactivityTimeoutInMinutes": 0,
    "name": "string",
    "parallelBuilds": 0,
    "parallelWorkspaces": 0,
    "pinnedWorkspaces": 0
  },
  "seats": 0,
  "start": "2019-08-24T14:15:22Z",
  "teamId": "string"
}
```

<h3 id="getactiveteamsubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Subscription](#schemasubscription)|

<aside class="success">
This operation does not require authentication
</aside>

## getTeamUsers

<a id="opIdgetTeamUsers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /team/{id}/users \
  -H 'Accept: application/json'

```

```http
GET /team/{id}/users HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/team/{id}/users',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/team/{id}/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/team/{id}/users', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/team/{id}/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/team/{id}/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /team/{id}/users`

<h3 id="getteamusers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "avatarUrl": "string",
    "disabled": true,
    "primaryEmail": "string",
    "suspendedUntil": "2019-08-24T14:15:22Z",
    "suspensionReason": "string",
    "teamRole": "owner",
    "userId": "string",
    "username": "string"
  }
]
```

<h3 id="getteamusers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getteamusers-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[TeamUser](#schemateamuser)]|false|none|none|
|» avatarUrl|string|false|none|AvatarUrl|
|» disabled|boolean|false|none|User account disabled flag|
|» primaryEmail|string|true|none|Primary email|
|» suspendedUntil|string(date-time)|false|none|Suspended until|
|» suspensionReason|string|false|none|Suspension reason|
|» teamRole|string|true|none|none|
|» userId|string|true|none|User id|
|» username|string|true|none|Name|

#### Enumerated Values

|Property|Value|
|---|---|
|teamRole|owner|
|teamRole|admin|
|teamRole|member|

<aside class="success">
This operation does not require authentication
</aside>

## leaveTeam

<a id="opIdleaveTeam"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /team/{id}/leave

```

```http
DELETE /team/{id}/leave HTTP/1.1

```

```javascript

fetch('/team/{id}/leave',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.delete '/team/{id}/leave',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/team/{id}/leave')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/team/{id}/leave', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/leave");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/team/{id}/leave", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /team/{id}/leave`

<h3 id="leaveteam-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

<h3 id="leaveteam-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|

<aside class="success">
This operation does not require authentication
</aside>

## removeTeamInvitation

<a id="opIdremoveTeamInvitation"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /team/{id}/invitation/{invitationId}

```

```http
DELETE /team/{id}/invitation/{invitationId} HTTP/1.1

```

```javascript

fetch('/team/{id}/invitation/{invitationId}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.delete '/team/{id}/invitation/{invitationId}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/team/{id}/invitation/{invitationId}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/team/{id}/invitation/{invitationId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/invitation/{invitationId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/team/{id}/invitation/{invitationId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /team/{id}/invitation/{invitationId}`

<h3 id="removeteaminvitation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|invitationId|path|string|true|none|

<h3 id="removeteaminvitation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|

<aside class="success">
This operation does not require authentication
</aside>

## removeUserFromTeam

<a id="opIdremoveUserFromTeam"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /team/{id}/users/{userId} \
  -H 'Accept: application/json'

```

```http
DELETE /team/{id}/users/{userId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/team/{id}/users/{userId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete '/team/{id}/users/{userId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/team/{id}/users/{userId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/team/{id}/users/{userId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/users/{userId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/team/{id}/users/{userId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /team/{id}/users/{userId}`

<h3 id="removeuserfromteam-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|userId|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "hasActiveSubscription": true,
  "id": "string",
  "name": "string",
  "privateMembers": true
}
```

<h3 id="removeuserfromteam-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Team](#schemateam)|

<aside class="success">
This operation does not require authentication
</aside>

## setUserTeamRole

<a id="opIdsetUserTeamRole"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /team/{id}/users/{userId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT /team/{id}/users/{userId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "teamRole": "owner"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/team/{id}/users/{userId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put '/team/{id}/users/{userId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/team/{id}/users/{userId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/team/{id}/users/{userId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/users/{userId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/team/{id}/users/{userId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /team/{id}/users/{userId}`

> Body parameter

```json
{
  "teamRole": "owner"
}
```

<h3 id="setuserteamrole-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|userId|path|string|true|none|
|body|body|[TeamUserRoleUpdate](#schemateamuserroleupdate)|true|none|

> Example responses

> 201 Response

```json
{
  "hasActiveSubscription": true,
  "id": "string",
  "name": "string",
  "privateMembers": true
}
```

<h3 id="setuserteamrole-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Team](#schemateam)|

<aside class="success">
This operation does not require authentication
</aside>

## updateTeamSubscription

<a id="opIdupdateTeamSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /team/{id}/subscriptions/{subscriptionId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT /team/{id}/subscriptions/{subscriptionId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "end": "2019-08-24T14:15:22Z",
  "planId": "string",
  "seats": 0,
  "start": "2019-08-24T14:15:22Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/team/{id}/subscriptions/{subscriptionId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put '/team/{id}/subscriptions/{subscriptionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/team/{id}/subscriptions/{subscriptionId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/team/{id}/subscriptions/{subscriptionId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/team/{id}/subscriptions/{subscriptionId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/team/{id}/subscriptions/{subscriptionId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /team/{id}/subscriptions/{subscriptionId}`

> Body parameter

```json
{
  "end": "2019-08-24T14:15:22Z",
  "planId": "string",
  "seats": 0,
  "start": "2019-08-24T14:15:22Z"
}
```

<h3 id="updateteamsubscription-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|subscriptionId|path|string|true|none|
|body|body|[SubscriptionUpdate](#schemasubscriptionupdate)|false|none|

> Example responses

> 200 Response

```json
{
  "disabled": true,
  "end": "2019-08-24T14:15:22Z",
  "id": "string",
  "plan": {
    "buildCredits": 0,
    "credits": 0,
    "id": "string",
    "inactivityTimeoutInMinutes": 0,
    "name": "string",
    "parallelBuilds": 0,
    "parallelWorkspaces": 0,
    "pinnedWorkspaces": 0
  },
  "seats": 0,
  "start": "2019-08-24T14:15:22Z",
  "teamId": "string"
}
```

<h3 id="updateteamsubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Subscription](#schemasubscription)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-gateway-plan">Plan</h1>

## createPlan

<a id="opIdcreatePlan"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /plan \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /plan HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "buildCredits": 0,
  "credits": 0,
  "id": "string",
  "inactivityTimeoutInMinutes": 0,
  "name": "string",
  "parallelBuilds": 0,
  "parallelWorkspaces": 0,
  "pinnedWorkspaces": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/plan',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '/plan',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/plan', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/plan', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/plan");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/plan", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /plan`

> Body parameter

```json
{
  "buildCredits": 0,
  "credits": 0,
  "id": "string",
  "inactivityTimeoutInMinutes": 0,
  "name": "string",
  "parallelBuilds": 0,
  "parallelWorkspaces": 0,
  "pinnedWorkspaces": 0
}
```

<h3 id="createplan-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PlanCreation](#schemaplancreation)|false|none|

> Example responses

> 200 Response

```json
{
  "buildCredits": 0,
  "credits": 0,
  "id": "string",
  "inactivityTimeoutInMinutes": 0,
  "name": "string",
  "parallelBuilds": 0,
  "parallelWorkspaces": 0,
  "pinnedWorkspaces": 0
}
```

<h3 id="createplan-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Plan](#schemaplan)|

<aside class="success">
This operation does not require authentication
</aside>

## getPlans

<a id="opIdgetPlans"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /plan \
  -H 'Accept: application/json'

```

```http
GET /plan HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/plan',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/plan',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/plan', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/plan', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/plan");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/plan", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /plan`

<h3 id="getplans-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|planId|query|string|false|none|
|name|query|string|false|none|
|limit|query|number|false|none|
|offset|query|number|false|none|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "buildCredits": 0,
      "credits": 0,
      "id": "string",
      "inactivityTimeoutInMinutes": 0,
      "name": "string",
      "parallelBuilds": 0,
      "parallelWorkspaces": 0,
      "pinnedWorkspaces": 0
    }
  ],
  "total": 0
}
```

<h3 id="getplans-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[PlanList](#schemaplanlist)|

<aside class="success">
This operation does not require authentication
</aside>

## deletePlan

<a id="opIddeletePlan"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /plan/{planId}

```

```http
DELETE /plan/{planId} HTTP/1.1

```

```javascript

fetch('/plan/{planId}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.delete '/plan/{planId}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/plan/{planId}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/plan/{planId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/plan/{planId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/plan/{planId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /plan/{planId}`

<h3 id="deleteplan-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|planId|path|string|true|none|

<h3 id="deleteplan-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|

<aside class="success">
This operation does not require authentication
</aside>

## getPlan

<a id="opIdgetPlan"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /plan/{planId} \
  -H 'Accept: application/json'

```

```http
GET /plan/{planId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/plan/{planId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/plan/{planId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/plan/{planId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/plan/{planId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/plan/{planId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/plan/{planId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /plan/{planId}`

<h3 id="getplan-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|planId|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "buildCredits": 0,
  "credits": 0,
  "id": "string",
  "inactivityTimeoutInMinutes": 0,
  "name": "string",
  "parallelBuilds": 0,
  "parallelWorkspaces": 0,
  "pinnedWorkspaces": 0
}
```

<h3 id="getplan-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Plan](#schemaplan)|

<aside class="success">
This operation does not require authentication
</aside>

## updatePlan

<a id="opIdupdatePlan"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /plan/{planId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT /plan/{planId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "buildCredits": 0,
  "credits": 0,
  "inactivityTimeoutInMinutes": 0,
  "name": "string",
  "parallelBuilds": 0,
  "parallelWorkspaces": 0,
  "pinnedWorkspaces": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/plan/{planId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put '/plan/{planId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/plan/{planId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/plan/{planId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/plan/{planId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/plan/{planId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /plan/{planId}`

> Body parameter

```json
{
  "buildCredits": 0,
  "credits": 0,
  "inactivityTimeoutInMinutes": 0,
  "name": "string",
  "parallelBuilds": 0,
  "parallelWorkspaces": 0,
  "pinnedWorkspaces": 0
}
```

<h3 id="updateplan-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|planId|path|string|true|none|
|body|body|[PlanUpdate](#schemaplanupdate)|false|none|

> Example responses

> 201 Response

```json
{
  "buildCredits": 0,
  "credits": 0,
  "id": "string",
  "inactivityTimeoutInMinutes": 0,
  "name": "string",
  "parallelBuilds": 0,
  "parallelWorkspaces": 0,
  "pinnedWorkspaces": 0
}
```

<h3 id="updateplan-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Plan](#schemaplan)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-gateway-workspaceusage">WorkspaceUsage</h1>

## getSpentCredits

<a id="opIdgetSpentCredits"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /workspace-usage/credits?periodStart=2019-08-24T14%3A15%3A22Z \
  -H 'Accept: application/json'

```

```http
GET /workspace-usage/credits?periodStart=2019-08-24T14%3A15%3A22Z HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/workspace-usage/credits?periodStart=2019-08-24T14%3A15%3A22Z',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/workspace-usage/credits',
  params: {
  'periodStart' => 'string(date-time)'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/workspace-usage/credits', params={
  'periodStart': '2019-08-24T14:15:22Z'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/workspace-usage/credits', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace-usage/credits?periodStart=2019-08-24T14%3A15%3A22Z");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/workspace-usage/credits", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /workspace-usage/credits`

<h3 id="getspentcredits-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|periodStart|query|string(date-time)|true|none|
|workspaceId|query|string|false|none|
|periodEnd|query|string(date-time)|false|none|
|teamId|query|string|false|none|

> Example responses

> 200 Response

```json
{
  "credits": 0
}
```

<h3 id="getspentcredits-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[WorkspaceUsageSpentCredit](#schemaworkspaceusagespentcredit)|

<aside class="success">
This operation does not require authentication
</aside>

## getWorkspaceUsageList

<a id="opIdgetWorkspaceUsageList"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /workspace-usage \
  -H 'Accept: application/json'

```

```http
GET /workspace-usage HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/workspace-usage',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/workspace-usage',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/workspace-usage', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/workspace-usage', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace-usage");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/workspace-usage", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /workspace-usage`

<h3 id="getworkspaceusagelist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|teamId|query|string|false|none|
|workspaceId|query|string|false|none|
|periodStart|query|string(date-time)|false|none|
|periodEnd|query|string(date-time)|false|none|
|limit|query|number|false|none|
|offset|query|number|false|none|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "creditsSpentPerMinute": 0,
      "teamId": "string",
      "usagePeriods": [
        {
          "creditsSpentPerMinute": 0,
          "startedAt": "string",
          "stoppedAt": "string",
          "workspaceInfo": {
            "createdFromTemplate": true,
            "gitContext": {
              "branch": "string",
              "cloneUrl": "string",
              "hasDevContainerConfig": true,
              "owner": "string",
              "path": "string",
              "prNumber": 0,
              "providerId": "string",
              "repo": "string",
              "sha": "string",
              "source": "string",
              "webUrl": "string"
            },
            "workspaceId": "string"
          }
        }
      ],
      "userId": "string",
      "workspaceId": "string"
    }
  ],
  "total": 0
}
```

<h3 id="getworkspaceusagelist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[WorkspaceUsageList](#schemaworkspaceusagelist)|

<aside class="success">
This operation does not require authentication
</aside>

## getWorkspaceUsagePeriodList

<a id="opIdgetWorkspaceUsagePeriodList"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /workspace-usage/periods \
  -H 'Accept: application/json'

```

```http
GET /workspace-usage/periods HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/workspace-usage/periods',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/workspace-usage/periods',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/workspace-usage/periods', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/workspace-usage/periods', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace-usage/periods");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/workspace-usage/periods", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /workspace-usage/periods`

<h3 id="getworkspaceusageperiodlist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|teamId|query|string|false|none|
|workspaceId|query|string|false|none|
|periodStart|query|string(date-time)|false|none|
|periodEnd|query|string(date-time)|false|none|
|limit|query|number|false|none|
|offset|query|number|false|none|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "creditsSpentPerMinute": 0,
      "startedAt": "string",
      "stoppedAt": "string",
      "workspaceInfo": {
        "createdFromTemplate": true,
        "gitContext": {
          "branch": "string",
          "cloneUrl": "string",
          "hasDevContainerConfig": true,
          "owner": "string",
          "path": "string",
          "prNumber": 0,
          "providerId": "string",
          "repo": "string",
          "sha": "string",
          "source": "string",
          "webUrl": "string"
        },
        "workspaceId": "string"
      }
    }
  ],
  "total": 0
}
```

<h3 id="getworkspaceusageperiodlist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[WorkspaceUsagePeriodList](#schemaworkspaceusageperiodlist)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-gateway-cluster">Cluster</h1>

## createCluster

<a id="opIdcreateCluster"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /cluster \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /cluster HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "config": "string",
  "domain": "string",
  "name": "string",
  "region": "us"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/cluster',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '/cluster',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/cluster', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/cluster', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/cluster");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/cluster", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /cluster`

> Body parameter

```json
{
  "config": "string",
  "domain": "string",
  "name": "string",
  "region": "us"
}
```

<h3 id="createcluster-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ClusterCreation](#schemaclustercreation)|false|none|

> Example responses

> 200 Response

```json
{
  "domain": "string",
  "id": "string",
  "name": "string",
  "region": "us"
}
```

<h3 id="createcluster-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Cluster](#schemacluster)|

<aside class="success">
This operation does not require authentication
</aside>

## getClusters

<a id="opIdgetClusters"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /cluster \
  -H 'Accept: application/json'

```

```http
GET /cluster HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/cluster',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/cluster',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/cluster', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/cluster', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/cluster");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/cluster", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /cluster`

<h3 id="getclusters-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|clusterId|query|string|false|none|
|name|query|string|false|none|
|limit|query|number|false|none|
|offset|query|number|false|none|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "domain": "string",
      "id": "string",
      "name": "string",
      "region": "us"
    }
  ],
  "total": 0
}
```

<h3 id="getclusters-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[ClusterList](#schemaclusterlist)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteCluster

<a id="opIddeleteCluster"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /cluster/{clusterId}

```

```http
DELETE /cluster/{clusterId} HTTP/1.1

```

```javascript

fetch('/cluster/{clusterId}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.delete '/cluster/{clusterId}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/cluster/{clusterId}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/cluster/{clusterId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/cluster/{clusterId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/cluster/{clusterId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /cluster/{clusterId}`

<h3 id="deletecluster-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|clusterId|path|string|true|none|

<h3 id="deletecluster-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|

<aside class="success">
This operation does not require authentication
</aside>

## getCluster

<a id="opIdgetCluster"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /cluster/{clusterId} \
  -H 'Accept: application/json'

```

```http
GET /cluster/{clusterId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/cluster/{clusterId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/cluster/{clusterId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/cluster/{clusterId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/cluster/{clusterId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/cluster/{clusterId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/cluster/{clusterId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /cluster/{clusterId}`

<h3 id="getcluster-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|clusterId|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "domain": "string",
  "id": "string",
  "name": "string",
  "region": "us"
}
```

<h3 id="getcluster-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Cluster](#schemacluster)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-gateway-workspaceinstance">WorkspaceInstance</h1>

## getActiveWorkspaceInstanceCount

<a id="opIdgetActiveWorkspaceInstanceCount"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /workspace-instance/active-workspaces?teamId=string \
  -H 'Accept: application/json'

```

```http
GET /workspace-instance/active-workspaces?teamId=string HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/workspace-instance/active-workspaces?teamId=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/workspace-instance/active-workspaces',
  params: {
  'teamId' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/workspace-instance/active-workspaces', params={
  'teamId': 'string'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/workspace-instance/active-workspaces', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace-instance/active-workspaces?teamId=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/workspace-instance/active-workspaces", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /workspace-instance/active-workspaces`

<h3 id="getactiveworkspaceinstancecount-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|teamId|query|string|true|none|

> Example responses

> 200 Response

```json
{
  "count": 0
}
```

<h3 id="getactiveworkspaceinstancecount-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[ActiveWorkspaceCount](#schemaactiveworkspacecount)|

<aside class="success">
This operation does not require authentication
</aside>

## startWorkspaceInstance

<a id="opIdstartWorkspaceInstance"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /workspace-instance/{id}/start \
  -H 'Accept: */*'

```

```http
POST /workspace-instance/{id}/start HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/workspace-instance/{id}/start',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/workspace-instance/{id}/start',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/workspace-instance/{id}/start', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/workspace-instance/{id}/start', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace-instance/{id}/start");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/workspace-instance/{id}/start", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /workspace-instance/{id}/start`

<h3 id="startworkspaceinstance-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="startworkspaceinstance-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="startworkspaceinstance-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## stopWorkspaceInstance

<a id="opIdstopWorkspaceInstance"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /workspace-instance/{id}/stop \
  -H 'Accept: */*'

```

```http
POST /workspace-instance/{id}/stop HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/workspace-instance/{id}/stop',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/workspace-instance/{id}/stop',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/workspace-instance/{id}/stop', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/workspace-instance/{id}/stop', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace-instance/{id}/stop");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/workspace-instance/{id}/stop", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /workspace-instance/{id}/stop`

<h3 id="stopworkspaceinstance-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="stopworkspaceinstance-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="stopworkspaceinstance-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-gateway-workspacessh">WorkspaceSsh</h1>

## getWorkspaceDetails

<a id="opIdgetWorkspaceDetails"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /workspace-ssh/{id} \
  -H 'Accept: application/json'

```

```http
GET /workspace-ssh/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/workspace-ssh/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/workspace-ssh/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/workspace-ssh/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/workspace-ssh/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace-ssh/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/workspace-ssh/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /workspace-ssh/{id}`

<h3 id="getworkspacedetails-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "createdAt": "2019-08-24T14:15:22Z",
  "createdFromTemplate": true,
  "destroyed": true,
  "error": "string",
  "errorLog": "string",
  "gitContext": {
    "branch": "string",
    "cloneUrl": "string",
    "hasDevContainerConfig": true,
    "owner": "string",
    "path": "string",
    "prNumber": 0,
    "providerId": "string",
    "repo": "string",
    "sha": "string",
    "source": "string",
    "webUrl": "string"
  },
  "gitStatus": {
    "ahead": 0,
    "behind": 0,
    "current": "string",
    "detached": true,
    "files": [
      {
        "from": "string",
        "index": "string",
        "path": "string",
        "workingDir": "string"
      }
    ],
    "tracking": "string"
  },
  "id": "string",
  "pinned": true,
  "shared": true,
  "sshAccessToken": "string",
  "teamId": "string",
  "updatedAt": "2019-08-24T14:15:22Z",
  "userId": "string",
  "version": 0,
  "workspaceInstance": {
    "className": "kata",
    "clusterId": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "error": "string",
    "errorLog": "string",
    "id": "string",
    "lastKeepAliveSignal": "2019-08-24T14:15:22Z",
    "startedAt": "2019-08-24T14:15:22Z",
    "state": "none",
    "stoppedAt": "2019-08-24T14:15:22Z",
    "token": "string",
    "updatedAt": "2019-08-24T14:15:22Z",
    "version": 0,
    "workspaceId": "string"
  }
}
```

<h3 id="getworkspacedetails-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Workspace](#schemaworkspace)|

<aside class="success">
This operation does not require authentication
</aside>

## receiveKeepAliveSignalFromSsh

<a id="opIdreceiveKeepAliveSignalFromSsh"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /workspace-ssh/{id}/keep-alive \
  -H 'Accept: */*'

```

```http
POST /workspace-ssh/{id}/keep-alive HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/workspace-ssh/{id}/keep-alive',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/workspace-ssh/{id}/keep-alive',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/workspace-ssh/{id}/keep-alive', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/workspace-ssh/{id}/keep-alive', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace-ssh/{id}/keep-alive");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/workspace-ssh/{id}/keep-alive", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /workspace-ssh/{id}/keep-alive`

<h3 id="receivekeepalivesignalfromssh-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="receivekeepalivesignalfromssh-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="receivekeepalivesignalfromssh-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## validatePublicKey

<a id="opIdvalidatePublicKey"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /workspace-ssh/{id}/validate/public-key \
  -H 'Accept: */*'

```

```http
GET /workspace-ssh/{id}/validate/public-key HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/workspace-ssh/{id}/validate/public-key',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get '/workspace-ssh/{id}/validate/public-key',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('/workspace-ssh/{id}/validate/public-key', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/workspace-ssh/{id}/validate/public-key', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace-ssh/{id}/validate/public-key");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/workspace-ssh/{id}/validate/public-key", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /workspace-ssh/{id}/validate/public-key`

<h3 id="validatepublickey-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|algo|query|string|false|none|
|blob|query|string|false|none|
|data|query|string|false|none|
|signature|query|string|false|none|

> Example responses

> 200 Response

<h3 id="validatepublickey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="validatepublickey-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## validateSshToken

<a id="opIdvalidateSshToken"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /workspace-ssh/{id}/validate/ssh-token \
  -H 'Accept: */*'

```

```http
GET /workspace-ssh/{id}/validate/ssh-token HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/workspace-ssh/{id}/validate/ssh-token',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get '/workspace-ssh/{id}/validate/ssh-token',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('/workspace-ssh/{id}/validate/ssh-token', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/workspace-ssh/{id}/validate/ssh-token', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/workspace-ssh/{id}/validate/ssh-token");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/workspace-ssh/{id}/validate/ssh-token", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /workspace-ssh/{id}/validate/ssh-token`

<h3 id="validatesshtoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|token|query|string|false|none|

> Example responses

> 200 Response

<h3 id="validatesshtoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="validatesshtoken-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-gateway-supervisor">Supervisor</h1>

## getGitCredentials

<a id="opIdgetGitCredentials"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /supervisor/git-credentials \
  -H 'Accept: application/json'

```

```http
GET /supervisor/git-credentials HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/supervisor/git-credentials',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/supervisor/git-credentials',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/supervisor/git-credentials', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/supervisor/git-credentials', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/git-credentials");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/supervisor/git-credentials", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /supervisor/git-credentials`

> Example responses

> 200 Response

```json
{
  "credentials": {
    "username": "string",
    "password": "string"
  },
  "email": "string",
  "username": "string"
}
```

<h3 id="getgitcredentials-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[GitCredentials](#schemagitcredentials)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## getInstanceState

<a id="opIdgetInstanceState"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /supervisor/state \
  -H 'Accept: application/json'

```

```http
GET /supervisor/state HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/supervisor/state',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/supervisor/state',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/supervisor/state', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/supervisor/state', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/state");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/supervisor/state", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /supervisor/state`

> Example responses

> 200 Response

```json
{
  "state": "none"
}
```

<h3 id="getinstancestate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[WorkspaceInstanceStateDTO](#schemaworkspaceinstancestatedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## setState

<a id="opIdsetState"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /supervisor/state \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST /supervisor/state HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "state": "none"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/supervisor/state',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post '/supervisor/state',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('/supervisor/state', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/supervisor/state', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/state");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/supervisor/state", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /supervisor/state`

> Body parameter

```json
{
  "state": "none"
}
```

<h3 id="setstate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[WorkspaceInstanceStateDTO](#schemaworkspaceinstancestatedto)|true|none|

> Example responses

> 200 Response

<h3 id="setstate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="setstate-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## getUserConfig

<a id="opIdgetUserConfig"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /supervisor/user-config \
  -H 'Accept: application/json'

```

```http
GET /supervisor/user-config HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/supervisor/user-config',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/supervisor/user-config',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/supervisor/user-config', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/supervisor/user-config', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/user-config");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/supervisor/user-config", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /supervisor/user-config`

> Example responses

> 200 Response

```json
{
  "dotfilesRepositoryUrl": "string",
  "primaryEmail": "string",
  "environmentVariables": [
    {
      "name": "string",
      "value": "string"
    }
  ]
}
```

<h3 id="getuserconfig-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[UserConfig](#schemauserconfig)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## getWorkspaceInstanceConfig

<a id="opIdgetWorkspaceInstanceConfig"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /supervisor/config \
  -H 'Accept: application/json'

```

```http
GET /supervisor/config HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/supervisor/config',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/supervisor/config',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/supervisor/config', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/supervisor/config', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/config");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/supervisor/config", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /supervisor/config`

> Example responses

> 200 Response

```json
{
  "createdFromTemplate": true,
  "domain": "string",
  "gitContext": {
    "branch": "string",
    "cloneUrl": "string",
    "hasDevContainerConfig": true,
    "owner": "string",
    "path": "string",
    "prNumber": 0,
    "providerId": "string",
    "repo": "string",
    "sha": "string",
    "source": "string",
    "webUrl": "string"
  },
  "gitCredentials": {
    "credentials": {
      "username": "string",
      "password": "string"
    },
    "email": "string",
    "username": "string"
  },
  "statusPageUrl": "string",
  "workspaceId": "string"
}
```

<h3 id="getworkspaceinstanceconfig-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[WorkspaceInstanceConfig](#schemaworkspaceinstanceconfig)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## receiveKeepAliveSignal

<a id="opIdreceiveKeepAliveSignal"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /supervisor/keep-alive \
  -H 'Accept: */*'

```

```http
POST /supervisor/keep-alive HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/supervisor/keep-alive',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/supervisor/keep-alive',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/supervisor/keep-alive', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/supervisor/keep-alive', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/keep-alive");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/supervisor/keep-alive", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /supervisor/keep-alive`

> Example responses

> 200 Response

<h3 id="receivekeepalivesignal-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="receivekeepalivesignal-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## setError

<a id="opIdsetError"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /supervisor/error \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST /supervisor/error HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "error": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/supervisor/error',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post '/supervisor/error',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('/supervisor/error', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/supervisor/error', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/error");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/supervisor/error", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /supervisor/error`

> Body parameter

```json
{
  "error": "string"
}
```

<h3 id="seterror-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[WorkspaceInstanceError](#schemaworkspaceinstanceerror)|true|none|

> Example responses

> 200 Response

<h3 id="seterror-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="seterror-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## setGitStatus

<a id="opIdsetGitStatus"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /supervisor/git-status \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST /supervisor/git-status HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "ahead": 0,
  "behind": 0,
  "current": "string",
  "detached": true,
  "files": [
    {
      "from": "string",
      "index": "string",
      "path": "string",
      "workingDir": "string"
    }
  ],
  "tracking": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/supervisor/git-status',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post '/supervisor/git-status',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('/supervisor/git-status', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/supervisor/git-status', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/git-status");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/supervisor/git-status", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /supervisor/git-status`

> Body parameter

```json
{
  "ahead": 0,
  "behind": 0,
  "current": "string",
  "detached": true,
  "files": [
    {
      "from": "string",
      "index": "string",
      "path": "string",
      "workingDir": "string"
    }
  ],
  "tracking": "string"
}
```

<h3 id="setgitstatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[WorkspaceGitStatus](#schemaworkspacegitstatus)|true|none|

> Example responses

> 200 Response

<h3 id="setgitstatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="setgitstatus-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## supervisorCreateUserEnvironmentVariable

<a id="opIdsupervisorCreateUserEnvironmentVariable"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /supervisor/user/environment-variables \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST /supervisor/user/environment-variables HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "name": "string",
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/supervisor/user/environment-variables',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post '/supervisor/user/environment-variables',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('/supervisor/user/environment-variables', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/supervisor/user/environment-variables', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/user/environment-variables");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/supervisor/user/environment-variables", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /supervisor/user/environment-variables`

> Body parameter

```json
{
  "name": "string",
  "value": "string"
}
```

<h3 id="supervisorcreateuserenvironmentvariable-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[EnvironmentVariableCreation](#schemaenvironmentvariablecreation)|false|none|

> Example responses

> 201 Response

<h3 id="supervisorcreateuserenvironmentvariable-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|Inline|

<h3 id="supervisorcreateuserenvironmentvariable-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## supervisorGetUserEnvironmentVariableList

<a id="opIdsupervisorGetUserEnvironmentVariableList"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /supervisor/user/environment-variables \
  -H 'Accept: application/json'

```

```http
GET /supervisor/user/environment-variables HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/supervisor/user/environment-variables',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/supervisor/user/environment-variables',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/supervisor/user/environment-variables', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/supervisor/user/environment-variables', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/user/environment-variables");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/supervisor/user/environment-variables", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /supervisor/user/environment-variables`

> Example responses

> 200 Response

```json
[
  {
    "name": "string",
    "value": "string"
  }
]
```

<h3 id="supervisorgetuserenvironmentvariablelist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="supervisorgetuserenvironmentvariablelist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[EnvironmentVariable](#schemaenvironmentvariable)]|false|none|none|
|» name|string|true|none|Name|
|» value|string|true|none|Value|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## supervisorDeleteUserEnvironmentVariable

<a id="opIdsupervisorDeleteUserEnvironmentVariable"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /supervisor/user/environment-variables/{name}

```

```http
DELETE /supervisor/user/environment-variables/{name} HTTP/1.1

```

```javascript

fetch('/supervisor/user/environment-variables/{name}',
{
  method: 'DELETE'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.delete '/supervisor/user/environment-variables/{name}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/supervisor/user/environment-variables/{name}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/supervisor/user/environment-variables/{name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/user/environment-variables/{name}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/supervisor/user/environment-variables/{name}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /supervisor/user/environment-variables/{name}`

<h3 id="supervisordeleteuserenvironmentvariable-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|name|path|string|true|none|

<h3 id="supervisordeleteuserenvironmentvariable-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## supervisorUpdateUserEnvironmentVariable

<a id="opIdsupervisorUpdateUserEnvironmentVariable"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /supervisor/user/environment-variables/{name} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT /supervisor/user/environment-variables/{name} HTTP/1.1

Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "name": "string",
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'
};

fetch('/supervisor/user/environment-variables/{name}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.put '/supervisor/user/environment-variables/{name}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('/supervisor/user/environment-variables/{name}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/supervisor/user/environment-variables/{name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/user/environment-variables/{name}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/supervisor/user/environment-variables/{name}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /supervisor/user/environment-variables/{name}`

> Body parameter

```json
{
  "name": "string",
  "value": "string"
}
```

<h3 id="supervisorupdateuserenvironmentvariable-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|name|path|string|true|none|
|body|body|[EnvironmentVariableUpdate](#schemaenvironmentvariableupdate)|false|none|

> Example responses

> 200 Response

<h3 id="supervisorupdateuserenvironmentvariable-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="supervisorupdateuserenvironmentvariable-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## supervisorGetWorkspace

<a id="opIdsupervisorGetWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /supervisor/workspace/{id} \
  -H 'Accept: application/json'

```

```http
GET /supervisor/workspace/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/supervisor/workspace/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/supervisor/workspace/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/supervisor/workspace/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/supervisor/workspace/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/workspace/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/supervisor/workspace/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /supervisor/workspace/{id}`

<h3 id="supervisorgetworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "createdAt": "2019-08-24T14:15:22Z",
  "createdFromTemplate": true,
  "destroyed": true,
  "error": "string",
  "errorLog": "string",
  "gitContext": {
    "branch": "string",
    "cloneUrl": "string",
    "hasDevContainerConfig": true,
    "owner": "string",
    "path": "string",
    "prNumber": 0,
    "providerId": "string",
    "repo": "string",
    "sha": "string",
    "source": "string",
    "webUrl": "string"
  },
  "gitStatus": {
    "ahead": 0,
    "behind": 0,
    "current": "string",
    "detached": true,
    "files": [
      {
        "from": "string",
        "index": "string",
        "path": "string",
        "workingDir": "string"
      }
    ],
    "tracking": "string"
  },
  "id": "string",
  "pinned": true,
  "shared": true,
  "sshAccessToken": "string",
  "teamId": "string",
  "updatedAt": "2019-08-24T14:15:22Z",
  "userId": "string",
  "version": 0,
  "workspaceInstance": {
    "className": "kata",
    "clusterId": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "error": "string",
    "errorLog": "string",
    "id": "string",
    "lastKeepAliveSignal": "2019-08-24T14:15:22Z",
    "startedAt": "2019-08-24T14:15:22Z",
    "state": "none",
    "stoppedAt": "2019-08-24T14:15:22Z",
    "token": "string",
    "updatedAt": "2019-08-24T14:15:22Z",
    "version": 0,
    "workspaceId": "string"
  }
}
```

<h3 id="supervisorgetworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Workspace](#schemaworkspace)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## supervisorPinWorkspace

<a id="opIdsupervisorPinWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /supervisor/workspace/{id}/pin \
  -H 'Accept: */*'

```

```http
POST /supervisor/workspace/{id}/pin HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/supervisor/workspace/{id}/pin',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/supervisor/workspace/{id}/pin',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/supervisor/workspace/{id}/pin', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/supervisor/workspace/{id}/pin', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/workspace/{id}/pin");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/supervisor/workspace/{id}/pin", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /supervisor/workspace/{id}/pin`

<h3 id="supervisorpinworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="supervisorpinworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="supervisorpinworkspace-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## supervisorShareWorkspace

<a id="opIdsupervisorShareWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /supervisor/workspace/{id}/share \
  -H 'Accept: */*'

```

```http
POST /supervisor/workspace/{id}/share HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/supervisor/workspace/{id}/share',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/supervisor/workspace/{id}/share',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/supervisor/workspace/{id}/share', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/supervisor/workspace/{id}/share', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/workspace/{id}/share");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/supervisor/workspace/{id}/share", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /supervisor/workspace/{id}/share`

<h3 id="supervisorshareworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="supervisorshareworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="supervisorshareworkspace-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## supervisorStopWorkspaceInstance

<a id="opIdsupervisorStopWorkspaceInstance"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /supervisor/workspace-instance/{id}/stop \
  -H 'Accept: */*'

```

```http
POST /supervisor/workspace-instance/{id}/stop HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/supervisor/workspace-instance/{id}/stop',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/supervisor/workspace-instance/{id}/stop',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/supervisor/workspace-instance/{id}/stop', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/supervisor/workspace-instance/{id}/stop', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/workspace-instance/{id}/stop");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/supervisor/workspace-instance/{id}/stop", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /supervisor/workspace-instance/{id}/stop`

<h3 id="supervisorstopworkspaceinstance-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="supervisorstopworkspaceinstance-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="supervisorstopworkspaceinstance-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## supervisorUnpinWorkspace

<a id="opIdsupervisorUnpinWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /supervisor/workspace/{id}/unpin \
  -H 'Accept: */*'

```

```http
POST /supervisor/workspace/{id}/unpin HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/supervisor/workspace/{id}/unpin',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/supervisor/workspace/{id}/unpin',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/supervisor/workspace/{id}/unpin', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/supervisor/workspace/{id}/unpin', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/workspace/{id}/unpin");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/supervisor/workspace/{id}/unpin", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /supervisor/workspace/{id}/unpin`

<h3 id="supervisorunpinworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="supervisorunpinworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="supervisorunpinworkspace-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## supervisorUnshareWorkspace

<a id="opIdsupervisorUnshareWorkspace"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /supervisor/workspace/{id}/unshare \
  -H 'Accept: */*'

```

```http
POST /supervisor/workspace/{id}/unshare HTTP/1.1

Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*'
};

fetch('/supervisor/workspace/{id}/unshare',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.post '/supervisor/workspace/{id}/unshare',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.post('/supervisor/workspace/{id}/unshare', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/supervisor/workspace/{id}/unshare', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/supervisor/workspace/{id}/unshare");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/supervisor/workspace/{id}/unshare", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /supervisor/workspace/{id}/unshare`

<h3 id="supervisorunshareworkspace-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

<h3 id="supervisorunshareworkspace-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="supervisorunshareworkspace-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

# Schemas

<h2 id="tocS_Workspace">Workspace</h2>
<!-- backwards compatibility -->
<a id="schemaworkspace"></a>
<a id="schema_Workspace"></a>
<a id="tocSworkspace"></a>
<a id="tocsworkspace"></a>

```json
{
  "createdAt": "2019-08-24T14:15:22Z",
  "createdFromTemplate": true,
  "destroyed": true,
  "error": "string",
  "errorLog": "string",
  "gitContext": {
    "branch": "string",
    "cloneUrl": "string",
    "hasDevContainerConfig": true,
    "owner": "string",
    "path": "string",
    "prNumber": 0,
    "providerId": "string",
    "repo": "string",
    "sha": "string",
    "source": "string",
    "webUrl": "string"
  },
  "gitStatus": {
    "ahead": 0,
    "behind": 0,
    "current": "string",
    "detached": true,
    "files": [
      {
        "from": "string",
        "index": "string",
        "path": "string",
        "workingDir": "string"
      }
    ],
    "tracking": "string"
  },
  "id": "string",
  "pinned": true,
  "shared": true,
  "sshAccessToken": "string",
  "teamId": "string",
  "updatedAt": "2019-08-24T14:15:22Z",
  "userId": "string",
  "version": 0,
  "workspaceInstance": {
    "className": "kata",
    "clusterId": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "error": "string",
    "errorLog": "string",
    "id": "string",
    "lastKeepAliveSignal": "2019-08-24T14:15:22Z",
    "startedAt": "2019-08-24T14:15:22Z",
    "state": "none",
    "stoppedAt": "2019-08-24T14:15:22Z",
    "token": "string",
    "updatedAt": "2019-08-24T14:15:22Z",
    "version": 0,
    "workspaceId": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|createdAt|string(date-time)|true|none|none|
|createdFromTemplate|boolean|true|none|none|
|destroyed|boolean|true|none|none|
|error|string|false|none|none|
|errorLog|string|false|none|none|
|gitContext|[GitContext](#schemagitcontext)|false|none|none|
|gitStatus|[WorkspaceGitStatus](#schemaworkspacegitstatus)|false|none|none|
|id|string|true|none|none|
|pinned|boolean|true|none|none|
|shared|boolean|true|none|none|
|sshAccessToken|string|false|none|none|
|teamId|string|true|none|none|
|updatedAt|string(date-time)|true|none|none|
|userId|string|true|none|none|
|version|number|true|none|none|
|workspaceInstance|[WorkspaceInstance](#schemaworkspaceinstance)|true|none|none|

<h2 id="tocS_GitContext">GitContext</h2>
<!-- backwards compatibility -->
<a id="schemagitcontext"></a>
<a id="schema_GitContext"></a>
<a id="tocSgitcontext"></a>
<a id="tocsgitcontext"></a>

```json
{
  "branch": "string",
  "cloneUrl": "string",
  "hasDevContainerConfig": true,
  "owner": "string",
  "path": "string",
  "prNumber": 0,
  "providerId": "string",
  "repo": "string",
  "sha": "string",
  "source": "string",
  "webUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|branch|string|false|none|The branch of the repository|
|cloneUrl|string|true|none|The clone url of the repository|
|hasDevContainerConfig|boolean|true|none|Has devcontainer config|
|owner|string|true|none|The owner of the repository|
|path|string|false|none|The path of the repository|
|prNumber|number|false|none|The pull request number of the repository|
|providerId|string|true|none|The id of the git provider|
|repo|string|true|none|The name of the repository|
|sha|string|true|none|The current commit sha of the repository|
|source|string|true|none|The source of the repository|
|webUrl|string|true|none|The web url of the repository|

<h2 id="tocS_WorkspaceGitStatus">WorkspaceGitStatus</h2>
<!-- backwards compatibility -->
<a id="schemaworkspacegitstatus"></a>
<a id="schema_WorkspaceGitStatus"></a>
<a id="tocSworkspacegitstatus"></a>
<a id="tocsworkspacegitstatus"></a>

```json
{
  "ahead": 0,
  "behind": 0,
  "current": "string",
  "detached": true,
  "files": [
    {
      "from": "string",
      "index": "string",
      "path": "string",
      "workingDir": "string"
    }
  ],
  "tracking": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ahead|integer|true|none|none|
|behind|integer|true|none|none|
|current|string|false|none|none|
|detached|boolean|true|none|none|
|files|[[WorkspaceFileStatus](#schemaworkspacefilestatus)]|true|none|none|
|tracking|string|false|none|none|

<h2 id="tocS_WorkspaceFileStatus">WorkspaceFileStatus</h2>
<!-- backwards compatibility -->
<a id="schemaworkspacefilestatus"></a>
<a id="schema_WorkspaceFileStatus"></a>
<a id="tocSworkspacefilestatus"></a>
<a id="tocsworkspacefilestatus"></a>

```json
{
  "from": "string",
  "index": "string",
  "path": "string",
  "workingDir": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|from|string|false|none|Original location of the file, when the file has been moved|
|index|string|false|none|First digit of the status code of the file, e.g. 'M' = modified. Represents the status of the index if no merge conflicts, otherwise represents status of one side of the merge.|
|path|string|false|none|Path of the file|
|workingDir|string|false|none|Second digit of the status code of the file. Represents status of the working directory if no merge conflicts, otherwise represents status of other side of a merge.|

<h2 id="tocS_WorkspaceInstance">WorkspaceInstance</h2>
<!-- backwards compatibility -->
<a id="schemaworkspaceinstance"></a>
<a id="schema_WorkspaceInstance"></a>
<a id="tocSworkspaceinstance"></a>
<a id="tocsworkspaceinstance"></a>

```json
{
  "className": "kata",
  "clusterId": "string",
  "createdAt": "2019-08-24T14:15:22Z",
  "error": "string",
  "errorLog": "string",
  "id": "string",
  "lastKeepAliveSignal": "2019-08-24T14:15:22Z",
  "startedAt": "2019-08-24T14:15:22Z",
  "state": "none",
  "stoppedAt": "2019-08-24T14:15:22Z",
  "token": "string",
  "updatedAt": "2019-08-24T14:15:22Z",
  "version": 0,
  "workspaceId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|className|string|true|none|none|
|clusterId|string|true|none|none|
|createdAt|string(date-time)|true|none|none|
|error|string|false|none|none|
|errorLog|string|false|none|none|
|id|string|true|none|none|
|lastKeepAliveSignal|string(date-time)|true|none|none|
|startedAt|string(date-time)|false|none|none|
|state|string|true|none|none|
|stoppedAt|string(date-time)|false|none|none|
|token|string|true|none|none|
|updatedAt|string(date-time)|true|none|none|
|version|number|true|none|none|
|workspaceId|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|className|kata|
|className|sysbox|
|className|default|
|state|none|
|state|initializing|
|state|pendingArchive|
|state|archiving|
|state|archived|
|state|pendingCreate|
|state|creating|
|state|created|
|state|pendingRestore|
|state|restoring|
|state|restored|
|state|pendingStop|
|state|stopping|
|state|stopped|
|state|pendingStart|
|state|starting|
|state|started|
|state|pendingDestroy|
|state|destroying|
|state|destroyed|
|state|error|

<h2 id="tocS_WorkspaceFromGitRepositoryUrlCreation">WorkspaceFromGitRepositoryUrlCreation</h2>
<!-- backwards compatibility -->
<a id="schemaworkspacefromgitrepositoryurlcreation"></a>
<a id="schema_WorkspaceFromGitRepositoryUrlCreation"></a>
<a id="tocSworkspacefromgitrepositoryurlcreation"></a>
<a id="tocsworkspacefromgitrepositoryurlcreation"></a>

```json
{
  "clusterId": "string",
  "createdFromTemplate": true,
  "gitRepositoryUrl": "string",
  "teamId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|clusterId|string|false|none|Cluster id|
|createdFromTemplate|boolean|false|none|Is the workspace created from a template?|
|gitRepositoryUrl|string|true|none|Git repository url|
|teamId|string|true|none|Workspace team id|

<h2 id="tocS_WorkspaceList">WorkspaceList</h2>
<!-- backwards compatibility -->
<a id="schemaworkspacelist"></a>
<a id="schema_WorkspaceList"></a>
<a id="tocSworkspacelist"></a>
<a id="tocsworkspacelist"></a>

```json
{
  "items": [
    {
      "createdAt": "2019-08-24T14:15:22Z",
      "createdFromTemplate": true,
      "destroyed": true,
      "error": "string",
      "errorLog": "string",
      "gitContext": {
        "branch": "string",
        "cloneUrl": "string",
        "hasDevContainerConfig": true,
        "owner": "string",
        "path": "string",
        "prNumber": 0,
        "providerId": "string",
        "repo": "string",
        "sha": "string",
        "source": "string",
        "webUrl": "string"
      },
      "gitStatus": {
        "ahead": 0,
        "behind": 0,
        "current": "string",
        "detached": true,
        "files": [
          {
            "from": "string",
            "index": "string",
            "path": "string",
            "workingDir": "string"
          }
        ],
        "tracking": "string"
      },
      "id": "string",
      "pinned": true,
      "shared": true,
      "sshAccessToken": "string",
      "teamId": "string",
      "updatedAt": "2019-08-24T14:15:22Z",
      "userId": "string",
      "version": 0,
      "workspaceInstance": {
        "className": "kata",
        "clusterId": "string",
        "createdAt": "2019-08-24T14:15:22Z",
        "error": "string",
        "errorLog": "string",
        "id": "string",
        "lastKeepAliveSignal": "2019-08-24T14:15:22Z",
        "startedAt": "2019-08-24T14:15:22Z",
        "state": "none",
        "stoppedAt": "2019-08-24T14:15:22Z",
        "token": "string",
        "updatedAt": "2019-08-24T14:15:22Z",
        "version": 0,
        "workspaceId": "string"
      }
    }
  ],
  "total": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[Workspace](#schemaworkspace)]|true|none|none|
|total|number|true|none|none|

<h2 id="tocS_EnvironmentVariableCreation">EnvironmentVariableCreation</h2>
<!-- backwards compatibility -->
<a id="schemaenvironmentvariablecreation"></a>
<a id="schema_EnvironmentVariableCreation"></a>
<a id="tocSenvironmentvariablecreation"></a>
<a id="tocsenvironmentvariablecreation"></a>

```json
{
  "name": "string",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Name|
|value|string|true|none|Value|

<h2 id="tocS_PublicSSHKeyCreation">PublicSSHKeyCreation</h2>
<!-- backwards compatibility -->
<a id="schemapublicsshkeycreation"></a>
<a id="schema_PublicSSHKeyCreation"></a>
<a id="tocSpublicsshkeycreation"></a>
<a id="tocspublicsshkeycreation"></a>

```json
{
  "expiresAt": "2019-08-24T14:15:22Z",
  "name": "My SSH key",
  "publicKey": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|expiresAt|string(date-time)|false|none|Expires at|
|name|string|true|none|SSH key name|
|publicKey|string|true|none|SSH key value|

<h2 id="tocS_User">User</h2>
<!-- backwards compatibility -->
<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "avatarUrl": "string",
  "disabled": true,
  "id": "string",
  "markedForDeletion": true,
  "preferences": {
    "defaultIde": "browser",
    "dotfilesRepositoryUrl": "string"
  },
  "primaryEmail": "string",
  "publicSSHKey": "string",
  "username": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|avatarUrl|string|false|none|AvatarUrl|
|disabled|boolean|false|none|User account disabled flag|
|id|string|true|none|Id|
|markedForDeletion|boolean|false|none|Marked for deletion|
|preferences|[UserPreferences](#schemauserpreferences)|true|none|none|
|primaryEmail|string|true|none|Primary email|
|publicSSHKey|string|true|none|Public SSH Key|
|username|string|true|none|Name|

<h2 id="tocS_UserPreferences">UserPreferences</h2>
<!-- backwards compatibility -->
<a id="schemauserpreferences"></a>
<a id="schema_UserPreferences"></a>
<a id="tocSuserpreferences"></a>
<a id="tocsuserpreferences"></a>

```json
{
  "defaultIde": "browser",
  "dotfilesRepositoryUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|defaultIde|string|true|none|Default IDE|
|dotfilesRepositoryUrl|string|false|none|Dotfiles repository URL|

#### Enumerated Values

|Property|Value|
|---|---|
|defaultIde|browser|
|defaultIde|vscode|
|defaultIde|jetbrains-iu|
|defaultIde|jetbrains-ic|
|defaultIde|jetbrains-ps|
|defaultIde|jetbrains-ws|
|defaultIde|jetbrains-py|
|defaultIde|jetbrains-pc|
|defaultIde|jetbrains-rm|
|defaultIde|jetbrains-cl|
|defaultIde|jetbrains-go|
|defaultIde|jetbrains-rd|

<h2 id="tocS_EnvironmentVariable">EnvironmentVariable</h2>
<!-- backwards compatibility -->
<a id="schemaenvironmentvariable"></a>
<a id="schema_EnvironmentVariable"></a>
<a id="tocSenvironmentvariable"></a>
<a id="tocsenvironmentvariable"></a>

```json
{
  "name": "string",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Name|
|value|string|true|none|Value|

<h2 id="tocS_GitNamespace">GitNamespace</h2>
<!-- backwards compatibility -->
<a id="schemagitnamespace"></a>
<a id="schema_GitNamespace"></a>
<a id="tocSgitnamespace"></a>
<a id="tocsgitnamespace"></a>

```json
{
  "id": "string",
  "name": "string",
  "personal": true,
  "provider": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|name|string|true|none|none|
|personal|boolean|false|none|none|
|provider|string|true|none|none|

<h2 id="tocS_GitRepositoryList">GitRepositoryList</h2>
<!-- backwards compatibility -->
<a id="schemagitrepositorylist"></a>
<a id="schema_GitRepositoryList"></a>
<a id="tocSgitrepositorylist"></a>
<a id="tocsgitrepositorylist"></a>

```json
{
  "items": [
    {
      "fullName": "string",
      "htmlUrl": "string",
      "name": "string"
    }
  ],
  "total": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[GitRepository](#schemagitrepository)]|true|none|none|
|total|number|true|none|none|

<h2 id="tocS_GitRepository">GitRepository</h2>
<!-- backwards compatibility -->
<a id="schemagitrepository"></a>
<a id="schema_GitRepository"></a>
<a id="tocSgitrepository"></a>
<a id="tocsgitrepository"></a>

```json
{
  "fullName": "string",
  "htmlUrl": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fullName|string|true|none|none|
|htmlUrl|string|true|none|none|
|name|string|true|none|none|

<h2 id="tocS_PublicSSHKey">PublicSSHKey</h2>
<!-- backwards compatibility -->
<a id="schemapublicsshkey"></a>
<a id="schema_PublicSSHKey"></a>
<a id="tocSpublicsshkey"></a>
<a id="tocspublicsshkey"></a>

```json
{
  "addedAt": "2019-08-24T14:15:22Z",
  "expiresAt": "2019-08-24T14:15:22Z",
  "id": "string",
  "name": "My SSH key"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|addedAt|string(date-time)|true|none|Added at|
|expiresAt|string(date-time)|false|none|Expires at|
|id|string|true|none|Id|
|name|string|true|none|SSH key name|

<h2 id="tocS_UserUpdateDefaultIde">UserUpdateDefaultIde</h2>
<!-- backwards compatibility -->
<a id="schemauserupdatedefaultide"></a>
<a id="schema_UserUpdateDefaultIde"></a>
<a id="tocSuserupdatedefaultide"></a>
<a id="tocsuserupdatedefaultide"></a>

```json
{
  "defaultIde": "browser"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|defaultIde|string|true|none|Default IDE|

#### Enumerated Values

|Property|Value|
|---|---|
|defaultIde|browser|
|defaultIde|vscode|
|defaultIde|jetbrains-iu|
|defaultIde|jetbrains-ic|
|defaultIde|jetbrains-ps|
|defaultIde|jetbrains-ws|
|defaultIde|jetbrains-py|
|defaultIde|jetbrains-pc|
|defaultIde|jetbrains-rm|
|defaultIde|jetbrains-cl|
|defaultIde|jetbrains-go|
|defaultIde|jetbrains-rd|

<h2 id="tocS_UserUpdateDotfilesRepositoryUrl">UserUpdateDotfilesRepositoryUrl</h2>
<!-- backwards compatibility -->
<a id="schemauserupdatedotfilesrepositoryurl"></a>
<a id="schema_UserUpdateDotfilesRepositoryUrl"></a>
<a id="tocSuserupdatedotfilesrepositoryurl"></a>
<a id="tocsuserupdatedotfilesrepositoryurl"></a>

```json
{
  "dotfilesRepositoryUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|dotfilesRepositoryUrl|string|false|none|Dotfiles repository URL|

<h2 id="tocS_EnvironmentVariableUpdate">EnvironmentVariableUpdate</h2>
<!-- backwards compatibility -->
<a id="schemaenvironmentvariableupdate"></a>
<a id="schema_EnvironmentVariableUpdate"></a>
<a id="tocSenvironmentvariableupdate"></a>
<a id="tocsenvironmentvariableupdate"></a>

```json
{
  "name": "string",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Name|
|value|string|true|none|Value|

<h2 id="tocS_Team">Team</h2>
<!-- backwards compatibility -->
<a id="schemateam"></a>
<a id="schema_Team"></a>
<a id="tocSteam"></a>
<a id="tocsteam"></a>

```json
{
  "hasActiveSubscription": true,
  "id": "string",
  "name": "string",
  "privateMembers": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|hasActiveSubscription|boolean|true|none|Team has active subscription|
|id|string|true|none|none|
|name|string|true|none|Name|
|privateMembers|boolean|true|none|Private members|

<h2 id="tocS_TeamCreation">TeamCreation</h2>
<!-- backwards compatibility -->
<a id="schemateamcreation"></a>
<a id="schema_TeamCreation"></a>
<a id="tocSteamcreation"></a>
<a id="tocsteamcreation"></a>

```json
{
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Name|

<h2 id="tocS_TeamInvitationCreation">TeamInvitationCreation</h2>
<!-- backwards compatibility -->
<a id="schemateaminvitationcreation"></a>
<a id="schema_TeamInvitationCreation"></a>
<a id="tocSteaminvitationcreation"></a>
<a id="tocsteaminvitationcreation"></a>

```json
{
  "email": "user@example.com",
  "expiresAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string(email)|true|none|Email|
|expiresAt|string(date-time)|false|none|Expires at|

<h2 id="tocS_SubscriptionCreation">SubscriptionCreation</h2>
<!-- backwards compatibility -->
<a id="schemasubscriptioncreation"></a>
<a id="schema_SubscriptionCreation"></a>
<a id="tocSsubscriptioncreation"></a>
<a id="tocssubscriptioncreation"></a>

```json
{
  "disabled": false,
  "end": "2019-08-24T14:15:22Z",
  "id": "string",
  "planId": "string",
  "seats": 0,
  "start": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|disabled|boolean|false|none|Disabled|
|end|string(date-time)|false|none|End|
|id|string|false|none|Subscription ID|
|planId|string|true|none|Plan id|
|seats|number|true|none|Max team members|
|start|string(date-time)|false|none|Start|

<h2 id="tocS_Subscription">Subscription</h2>
<!-- backwards compatibility -->
<a id="schemasubscription"></a>
<a id="schema_Subscription"></a>
<a id="tocSsubscription"></a>
<a id="tocssubscription"></a>

```json
{
  "disabled": true,
  "end": "2019-08-24T14:15:22Z",
  "id": "string",
  "plan": {
    "buildCredits": 0,
    "credits": 0,
    "id": "string",
    "inactivityTimeoutInMinutes": 0,
    "name": "string",
    "parallelBuilds": 0,
    "parallelWorkspaces": 0,
    "pinnedWorkspaces": 0
  },
  "seats": 0,
  "start": "2019-08-24T14:15:22Z",
  "teamId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|disabled|boolean|true|none|Disabled|
|end|string(date-time)|false|none|End|
|id|string|true|none|none|
|plan|[Plan](#schemaplan)|true|none|none|
|seats|number|true|none|Max team members|
|start|string(date-time)|true|none|Start|
|teamId|string|true|none|Team id|

<h2 id="tocS_Plan">Plan</h2>
<!-- backwards compatibility -->
<a id="schemaplan"></a>
<a id="schema_Plan"></a>
<a id="tocSplan"></a>
<a id="tocsplan"></a>

```json
{
  "buildCredits": 0,
  "credits": 0,
  "id": "string",
  "inactivityTimeoutInMinutes": 0,
  "name": "string",
  "parallelBuilds": 0,
  "parallelWorkspaces": 0,
  "pinnedWorkspaces": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|buildCredits|number|true|none|Build credits|
|credits|number|true|none|Workspace credits|
|id|string|true|none|none|
|inactivityTimeoutInMinutes|number|true|none|Inactivity timeout in minutes|
|name|string|true|none|Name|
|parallelBuilds|number|true|none|Parallel builds|
|parallelWorkspaces|number|true|none|Parallel workspaces|
|pinnedWorkspaces|number|true|none|Limit of pinned workspaces|

<h2 id="tocS_TeamInvitation">TeamInvitation</h2>
<!-- backwards compatibility -->
<a id="schemateaminvitation"></a>
<a id="schema_TeamInvitation"></a>
<a id="tocSteaminvitation"></a>
<a id="tocsteaminvitation"></a>

```json
{
  "email": "user@example.com",
  "expiresAt": "2019-08-24T14:15:22Z",
  "id": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string(email)|true|none|none|
|expiresAt|string(date-time)|true|none|none|
|id|string|true|none|Invitation Id|

<h2 id="tocS_TeamUser">TeamUser</h2>
<!-- backwards compatibility -->
<a id="schemateamuser"></a>
<a id="schema_TeamUser"></a>
<a id="tocSteamuser"></a>
<a id="tocsteamuser"></a>

```json
{
  "avatarUrl": "string",
  "disabled": true,
  "primaryEmail": "string",
  "suspendedUntil": "2019-08-24T14:15:22Z",
  "suspensionReason": "string",
  "teamRole": "owner",
  "userId": "string",
  "username": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|avatarUrl|string|false|none|AvatarUrl|
|disabled|boolean|false|none|User account disabled flag|
|primaryEmail|string|true|none|Primary email|
|suspendedUntil|string(date-time)|false|none|Suspended until|
|suspensionReason|string|false|none|Suspension reason|
|teamRole|string|true|none|none|
|userId|string|true|none|User id|
|username|string|true|none|Name|

#### Enumerated Values

|Property|Value|
|---|---|
|teamRole|owner|
|teamRole|admin|
|teamRole|member|

<h2 id="tocS_TeamUserRoleUpdate">TeamUserRoleUpdate</h2>
<!-- backwards compatibility -->
<a id="schemateamuserroleupdate"></a>
<a id="schema_TeamUserRoleUpdate"></a>
<a id="tocSteamuserroleupdate"></a>
<a id="tocsteamuserroleupdate"></a>

```json
{
  "teamRole": "owner"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|teamRole|string|true|none|Team role|

#### Enumerated Values

|Property|Value|
|---|---|
|teamRole|owner|
|teamRole|admin|
|teamRole|member|

<h2 id="tocS_TeamUpdate">TeamUpdate</h2>
<!-- backwards compatibility -->
<a id="schemateamupdate"></a>
<a id="schema_TeamUpdate"></a>
<a id="tocSteamupdate"></a>
<a id="tocsteamupdate"></a>

```json
{
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Team name|

<h2 id="tocS_SubscriptionUpdate">SubscriptionUpdate</h2>
<!-- backwards compatibility -->
<a id="schemasubscriptionupdate"></a>
<a id="schema_SubscriptionUpdate"></a>
<a id="tocSsubscriptionupdate"></a>
<a id="tocssubscriptionupdate"></a>

```json
{
  "end": "2019-08-24T14:15:22Z",
  "planId": "string",
  "seats": 0,
  "start": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|end|string(date-time)|false|none|End|
|planId|string|true|none|Plan id|
|seats|number|true|none|Max team members|
|start|string(date-time)|true|none|Start|

<h2 id="tocS_PlanCreation">PlanCreation</h2>
<!-- backwards compatibility -->
<a id="schemaplancreation"></a>
<a id="schema_PlanCreation"></a>
<a id="tocSplancreation"></a>
<a id="tocsplancreation"></a>

```json
{
  "buildCredits": 0,
  "credits": 0,
  "id": "string",
  "inactivityTimeoutInMinutes": 0,
  "name": "string",
  "parallelBuilds": 0,
  "parallelWorkspaces": 0,
  "pinnedWorkspaces": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|buildCredits|number|true|none|Build credits|
|credits|number|true|none|Workspace hours|
|id|string|false|none|Id|
|inactivityTimeoutInMinutes|number|true|none|Inactivity timeout in minutes|
|name|string|true|none|Name|
|parallelBuilds|number|true|none|Parallel builds|
|parallelWorkspaces|number|true|none|Parallel workspaces|
|pinnedWorkspaces|number|true|none|Limit of pinned workspaces|

<h2 id="tocS_PlanList">PlanList</h2>
<!-- backwards compatibility -->
<a id="schemaplanlist"></a>
<a id="schema_PlanList"></a>
<a id="tocSplanlist"></a>
<a id="tocsplanlist"></a>

```json
{
  "items": [
    {
      "buildCredits": 0,
      "credits": 0,
      "id": "string",
      "inactivityTimeoutInMinutes": 0,
      "name": "string",
      "parallelBuilds": 0,
      "parallelWorkspaces": 0,
      "pinnedWorkspaces": 0
    }
  ],
  "total": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[Plan](#schemaplan)]|true|none|none|
|total|number|true|none|none|

<h2 id="tocS_PlanUpdate">PlanUpdate</h2>
<!-- backwards compatibility -->
<a id="schemaplanupdate"></a>
<a id="schema_PlanUpdate"></a>
<a id="tocSplanupdate"></a>
<a id="tocsplanupdate"></a>

```json
{
  "buildCredits": 0,
  "credits": 0,
  "inactivityTimeoutInMinutes": 0,
  "name": "string",
  "parallelBuilds": 0,
  "parallelWorkspaces": 0,
  "pinnedWorkspaces": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|buildCredits|number|true|none|Build credits|
|credits|number|true|none|Workspace credits|
|inactivityTimeoutInMinutes|number|true|none|Inactivity timeout in minutes|
|name|string|true|none|Name|
|parallelBuilds|number|true|none|Parallel builds|
|parallelWorkspaces|number|true|none|Parallel workspaces|
|pinnedWorkspaces|number|true|none|Limit of pinned workspaces|

<h2 id="tocS_WorkspaceUsageSpentCredit">WorkspaceUsageSpentCredit</h2>
<!-- backwards compatibility -->
<a id="schemaworkspaceusagespentcredit"></a>
<a id="schema_WorkspaceUsageSpentCredit"></a>
<a id="tocSworkspaceusagespentcredit"></a>
<a id="tocsworkspaceusagespentcredit"></a>

```json
{
  "credits": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|credits|number|true|none|Credits spent per minute|

<h2 id="tocS_WorkspaceUsageList">WorkspaceUsageList</h2>
<!-- backwards compatibility -->
<a id="schemaworkspaceusagelist"></a>
<a id="schema_WorkspaceUsageList"></a>
<a id="tocSworkspaceusagelist"></a>
<a id="tocsworkspaceusagelist"></a>

```json
{
  "items": [
    {
      "creditsSpentPerMinute": 0,
      "teamId": "string",
      "usagePeriods": [
        {
          "creditsSpentPerMinute": 0,
          "startedAt": "string",
          "stoppedAt": "string",
          "workspaceInfo": {
            "createdFromTemplate": true,
            "gitContext": {
              "branch": "string",
              "cloneUrl": "string",
              "hasDevContainerConfig": true,
              "owner": "string",
              "path": "string",
              "prNumber": 0,
              "providerId": "string",
              "repo": "string",
              "sha": "string",
              "source": "string",
              "webUrl": "string"
            },
            "workspaceId": "string"
          }
        }
      ],
      "userId": "string",
      "workspaceId": "string"
    }
  ],
  "total": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[WorkspaceUsage](#schemaworkspaceusage)]|true|none|none|
|total|number|true|none|none|

<h2 id="tocS_WorkspaceUsage">WorkspaceUsage</h2>
<!-- backwards compatibility -->
<a id="schemaworkspaceusage"></a>
<a id="schema_WorkspaceUsage"></a>
<a id="tocSworkspaceusage"></a>
<a id="tocsworkspaceusage"></a>

```json
{
  "creditsSpentPerMinute": 0,
  "teamId": "string",
  "usagePeriods": [
    {
      "creditsSpentPerMinute": 0,
      "startedAt": "string",
      "stoppedAt": "string",
      "workspaceInfo": {
        "createdFromTemplate": true,
        "gitContext": {
          "branch": "string",
          "cloneUrl": "string",
          "hasDevContainerConfig": true,
          "owner": "string",
          "path": "string",
          "prNumber": 0,
          "providerId": "string",
          "repo": "string",
          "sha": "string",
          "source": "string",
          "webUrl": "string"
        },
        "workspaceId": "string"
      }
    }
  ],
  "userId": "string",
  "workspaceId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|creditsSpentPerMinute|number|true|none|Credits spent per minute|
|teamId|string|true|none|Team Id|
|usagePeriods|[[WorkspaceUsagePeriod](#schemaworkspaceusageperiod)]|true|none|Usage periods|
|userId|string|true|none|User Id|
|workspaceId|string|true|none|Workspace Id|

<h2 id="tocS_WorkspaceUsagePeriod">WorkspaceUsagePeriod</h2>
<!-- backwards compatibility -->
<a id="schemaworkspaceusageperiod"></a>
<a id="schema_WorkspaceUsagePeriod"></a>
<a id="tocSworkspaceusageperiod"></a>
<a id="tocsworkspaceusageperiod"></a>

```json
{
  "creditsSpentPerMinute": 0,
  "startedAt": "string",
  "stoppedAt": "string",
  "workspaceInfo": {
    "createdFromTemplate": true,
    "gitContext": {
      "branch": "string",
      "cloneUrl": "string",
      "hasDevContainerConfig": true,
      "owner": "string",
      "path": "string",
      "prNumber": 0,
      "providerId": "string",
      "repo": "string",
      "sha": "string",
      "source": "string",
      "webUrl": "string"
    },
    "workspaceId": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|creditsSpentPerMinute|number|true|none|Credits spent per minute|
|startedAt|string|true|none|Usage started at|
|stoppedAt|string|false|none|Usage stopped at|
|workspaceInfo|[WorkspaceUsageWorkspaceInfo](#schemaworkspaceusageworkspaceinfo)|true|none|none|

<h2 id="tocS_WorkspaceUsageWorkspaceInfo">WorkspaceUsageWorkspaceInfo</h2>
<!-- backwards compatibility -->
<a id="schemaworkspaceusageworkspaceinfo"></a>
<a id="schema_WorkspaceUsageWorkspaceInfo"></a>
<a id="tocSworkspaceusageworkspaceinfo"></a>
<a id="tocsworkspaceusageworkspaceinfo"></a>

```json
{
  "createdFromTemplate": true,
  "gitContext": {
    "branch": "string",
    "cloneUrl": "string",
    "hasDevContainerConfig": true,
    "owner": "string",
    "path": "string",
    "prNumber": 0,
    "providerId": "string",
    "repo": "string",
    "sha": "string",
    "source": "string",
    "webUrl": "string"
  },
  "workspaceId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|createdFromTemplate|boolean|true|none|Created from template?|
|gitContext|[GitContext](#schemagitcontext)|true|none|none|
|workspaceId|string|true|none|Workspace ID|

<h2 id="tocS_WorkspaceUsagePeriodList">WorkspaceUsagePeriodList</h2>
<!-- backwards compatibility -->
<a id="schemaworkspaceusageperiodlist"></a>
<a id="schema_WorkspaceUsagePeriodList"></a>
<a id="tocSworkspaceusageperiodlist"></a>
<a id="tocsworkspaceusageperiodlist"></a>

```json
{
  "items": [
    {
      "creditsSpentPerMinute": 0,
      "startedAt": "string",
      "stoppedAt": "string",
      "workspaceInfo": {
        "createdFromTemplate": true,
        "gitContext": {
          "branch": "string",
          "cloneUrl": "string",
          "hasDevContainerConfig": true,
          "owner": "string",
          "path": "string",
          "prNumber": 0,
          "providerId": "string",
          "repo": "string",
          "sha": "string",
          "source": "string",
          "webUrl": "string"
        },
        "workspaceId": "string"
      }
    }
  ],
  "total": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[WorkspaceUsagePeriod](#schemaworkspaceusageperiod)]|true|none|none|
|total|number|true|none|none|

<h2 id="tocS_Cluster">Cluster</h2>
<!-- backwards compatibility -->
<a id="schemacluster"></a>
<a id="schema_Cluster"></a>
<a id="tocScluster"></a>
<a id="tocscluster"></a>

```json
{
  "domain": "string",
  "id": "string",
  "name": "string",
  "region": "us"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|domain|string|true|none|Domain|
|id|string|true|none|none|
|name|string|true|none|Name|
|region|string|false|none|Region|

#### Enumerated Values

|Property|Value|
|---|---|
|region|us|
|region|eu|
|region|asia|
|region|local|

<h2 id="tocS_ClusterCreation">ClusterCreation</h2>
<!-- backwards compatibility -->
<a id="schemaclustercreation"></a>
<a id="schema_ClusterCreation"></a>
<a id="tocSclustercreation"></a>
<a id="tocsclustercreation"></a>

```json
{
  "config": "string",
  "domain": "string",
  "name": "string",
  "region": "us"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|config|string|true|none|Cluster config|
|domain|string|true|none|Domain|
|name|string|true|none|Name|
|region|string|true|none|Region|

#### Enumerated Values

|Property|Value|
|---|---|
|region|us|
|region|eu|
|region|asia|
|region|local|

<h2 id="tocS_ClusterList">ClusterList</h2>
<!-- backwards compatibility -->
<a id="schemaclusterlist"></a>
<a id="schema_ClusterList"></a>
<a id="tocSclusterlist"></a>
<a id="tocsclusterlist"></a>

```json
{
  "items": [
    {
      "domain": "string",
      "id": "string",
      "name": "string",
      "region": "us"
    }
  ],
  "total": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[Cluster](#schemacluster)]|true|none|none|
|total|number|true|none|none|

<h2 id="tocS_ActiveWorkspaceCount">ActiveWorkspaceCount</h2>
<!-- backwards compatibility -->
<a id="schemaactiveworkspacecount"></a>
<a id="schema_ActiveWorkspaceCount"></a>
<a id="tocSactiveworkspacecount"></a>
<a id="tocsactiveworkspacecount"></a>

```json
{
  "count": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|number|true|none|Active workspace count|

<h2 id="tocS_GitCredentials">GitCredentials</h2>
<!-- backwards compatibility -->
<a id="schemagitcredentials"></a>
<a id="schema_GitCredentials"></a>
<a id="tocSgitcredentials"></a>
<a id="tocsgitcredentials"></a>

```json
{
  "credentials": {
    "username": "string",
    "password": "string"
  },
  "email": "string",
  "username": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|credentials|[Credentials](#schemacredentials)|true|none|none|
|email|string|false|none|Email|
|username|string|true|none|Username|

<h2 id="tocS_Credentials">Credentials</h2>
<!-- backwards compatibility -->
<a id="schemacredentials"></a>
<a id="schema_Credentials"></a>
<a id="tocScredentials"></a>
<a id="tocscredentials"></a>

```json
{
  "username": "string",
  "password": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|true|none|Username|
|password|string|true|none|Password|

<h2 id="tocS_WorkspaceInstanceStateDTO">WorkspaceInstanceStateDTO</h2>
<!-- backwards compatibility -->
<a id="schemaworkspaceinstancestatedto"></a>
<a id="schema_WorkspaceInstanceStateDTO"></a>
<a id="tocSworkspaceinstancestatedto"></a>
<a id="tocsworkspaceinstancestatedto"></a>

```json
{
  "state": "none"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|state|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|state|none|
|state|initializing|
|state|pendingArchive|
|state|archiving|
|state|archived|
|state|pendingCreate|
|state|creating|
|state|created|
|state|pendingRestore|
|state|restoring|
|state|restored|
|state|pendingStop|
|state|stopping|
|state|stopped|
|state|pendingStart|
|state|starting|
|state|started|
|state|pendingDestroy|
|state|destroying|
|state|destroyed|
|state|error|

<h2 id="tocS_UserConfig">UserConfig</h2>
<!-- backwards compatibility -->
<a id="schemauserconfig"></a>
<a id="schema_UserConfig"></a>
<a id="tocSuserconfig"></a>
<a id="tocsuserconfig"></a>

```json
{
  "dotfilesRepositoryUrl": "string",
  "primaryEmail": "string",
  "environmentVariables": [
    {
      "name": "string",
      "value": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|dotfilesRepositoryUrl|string|false|none|Dotfiles repository URL|
|primaryEmail|string|false|none|Primary email|
|environmentVariables|[[EnvironmentVariable](#schemaenvironmentvariable)]|true|none|none|

<h2 id="tocS_WorkspaceInstanceConfig">WorkspaceInstanceConfig</h2>
<!-- backwards compatibility -->
<a id="schemaworkspaceinstanceconfig"></a>
<a id="schema_WorkspaceInstanceConfig"></a>
<a id="tocSworkspaceinstanceconfig"></a>
<a id="tocsworkspaceinstanceconfig"></a>

```json
{
  "createdFromTemplate": true,
  "domain": "string",
  "gitContext": {
    "branch": "string",
    "cloneUrl": "string",
    "hasDevContainerConfig": true,
    "owner": "string",
    "path": "string",
    "prNumber": 0,
    "providerId": "string",
    "repo": "string",
    "sha": "string",
    "source": "string",
    "webUrl": "string"
  },
  "gitCredentials": {
    "credentials": {
      "username": "string",
      "password": "string"
    },
    "email": "string",
    "username": "string"
  },
  "statusPageUrl": "string",
  "workspaceId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|createdFromTemplate|boolean|true|none|Created from template|
|domain|string|true|none|Domain|
|gitContext|[GitContext](#schemagitcontext)|true|none|none|
|gitCredentials|[GitCredentials](#schemagitcredentials)|true|none|none|
|statusPageUrl|string|true|none|Status page url|
|workspaceId|string|true|none|Workspace id|

<h2 id="tocS_WorkspaceInstanceError">WorkspaceInstanceError</h2>
<!-- backwards compatibility -->
<a id="schemaworkspaceinstanceerror"></a>
<a id="schema_WorkspaceInstanceError"></a>
<a id="tocSworkspaceinstanceerror"></a>
<a id="tocsworkspaceinstanceerror"></a>

```json
{
  "error": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|error|string|true|none|none|


