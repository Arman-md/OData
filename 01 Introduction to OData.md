<img width="1197" height="666" alt="image" src="https://github.com/user-attachments/assets/f305f4dc-fd12-4111-a1b9-f30de14d6ecf" />##
<img width="1115" height="416" alt="image" src="https://github.com/user-attachments/assets/094de616-ae69-4882-97ba-c1b94d05d11d" />

##

<img width="1220" height="638" alt="image" src="https://github.com/user-attachments/assets/7cf0d429-610e-42c8-aa4b-dba8fce9ab5f" />

##

<img width="1215" height="443" alt="image" src="https://github.com/user-attachments/assets/f7112c46-7211-4860-aa35-d21b68d8d396" />

##

<img width="1206" height="680" alt="image" src="https://github.com/user-attachments/assets/bca43e9f-32f7-4137-abfb-ffb83dd37fe8" />

# An API, If to be called as a REST API, It needs to have the following properties:

# 1 🌐 Uniform Interface in REST API

The **Uniform Interface** is one of the key principles of REST (Representational State Transfer). It ensures that all interactions between clients and servers follow a consistent and predictable pattern.

---



## ✅ Why is Uniform Interface Important?

- Makes APIs **easy to understand**
- Allows **independent evolution** of client and server
- Improves **interoperability** between systems
- Supports **scalability** and **simplicity**

---

## 🔑 Key Principles of Uniform Interface

## 1. **Resource-Based Design**
- Everything is treated as a **resource** (like a user, product, or order).
- Each resource is identified by a **URI** (Uniform Resource Identifier).

**Example: to get a User**

```http
GET /users/123

```

<img width="1197" height="666" alt="image" src="https://github.com/user-attachments/assets/0d8c8ed7-bd30-4890-bed4-6f9d16830758" />

### Basically to summarize

`The server should send the representation of the data, based on the request from the client which will come in the form of a URI( Uniform Resource Identifier)`
`It should be having enough data( along with metadata) such that the client should understand...`


## 2. Standard HTTP Methods
REST uses standard HTTP methods to perform actions on resources:

Method	Action	Example
`GET	Read data	GET /products/10`
`POST	Create new data	POST /orders`
`PUT	Update data	PUT /users/123`
`DELETE	Remove data	DELETE /users/123`


## 3. Resource Representation
Resources are not sent directly. Instead, they are represented in formats like JSON or XML.

Example JSON Response:

``` JSON
{
  "id": 123,
  "name": "Arman",
  "role": "SAP ABAP Developer"
}

```

## 4. Stateless Communication

server doesn't store the information of the client

Each request must contain all the information needed to process it. The server does not remember previous requests.

Example:


``` JSON

GET /users/123
Authorization: Bearer <token>
```

Even if you made a previous request, this one must include the token again.

## 5. Self-Descriptive Messages

Requests and responses should include enough information to understand how to handle them.

Example:

``` JSON

Content-Type: application/json

This tells the server that the request body is in JSON format.
```

## 6. HATEOAS (Hypermedia as the Engine of Application State)
Responses can include links to other actions or resources, guiding the client on what to do next.

Example Response:

``` JSON
{
  "id": 123,
  "name": "Arman",
  "links": [
    { "rel": "update", "href": "/users/123", "method": "PUT" },
    { "rel": "delete", "href": "/users/123", "method": "DELETE" }
  ]
}

```
📘 Real-World Example (SAP OData)
In SAP OData services, you might access a material like this:

``` JSON

GET /sap/opu/odata/sap/ZMATERIAL_SRV/MaterialSet('MAT123')
```

This follows the resource-based pattern.
Uses GET to retrieve data.
Returns JSON representation of the material.
Is stateless and self-descriptive.

## 7 Layered system
<img width="1187" height="668" alt="image" src="https://github.com/user-attachments/assets/fbafb86f-4d62-4a5f-b301-2453d1062125" />



## 8 Cacheability( Client will store some repetative information ( metadata/resources ) of Server 

<img width="1190" height="675" alt="image" src="https://github.com/user-attachments/assets/28e4f602-1bfb-4e76-a121-0d3517ba0f01" />


## 9 Code on demand(optional)

<img width="1188" height="431" alt="image" src="https://github.com/user-attachments/assets/5f9ce143-a1b6-4db7-bec5-8f53f1726823" />

















