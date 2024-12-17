# StadiumGoods Unofficial API Documentation

## Overview
The StadiumGoods API provides comprehensive access to product information, search capabilities, and collections for sneakers and related merchandise. This API allows developers to retrieve product details, search for items, explore collections, and more.

This API is listed on [RapidAPI](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/stadium-goods-api): https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/stadium-goods-api
## Base URL
```
https://stadium-goods-api.p.rapidapi.com
```

## Authentication
*Note: Authentication details should be replaced with actual credentials from your RapidAPI API Key*
- API Key required in headers
- Method: API Key
- Header Name: `X-RapidAPI-Key`

## Endpoints

### 1. Product Search
```
GET /products/search
```
**Description:** Search for products based on a query string

**Parameters:**
- `query` (required): Search term for products
- `page` (optional, default: 1): Page number of results

**Response:**
```json
{
  "status": "success",
  "data": [/* Product Results */],
  "message": null
}
```

### 2. Product Description
```
GET /products/description
```
**Description:** Retrieve detailed information about a specific product

**Parameters:**
- `productUrl` (required): URL of the specific product

**Response:**
```json
{
  "status": "success", 
  "data": {/* Product Details */},
  "message": null
}
```

### 3. Similar Products
```
GET /products/similar
```
**Description:** Find similar products based on a product ID

**Parameters:**
- `productId` (required): Base product ID
- `limit` (optional, default: 7): Number of similar products to return

**Response:**
```json
{
  "status": "success",
  "data": [/* Similar Products */],
  "message": null
}
```

### 4. Collections
```
GET /collections
```
**Description:** Retrieve available product collections

**Parameters:**
- `page` (optional, default: 1): Page number of collections

**Response:**
```json
{
  "status": "success",
  "data": [/* Collections */],
  "message": null
}
```

### 5. Collection Products
```
GET /collections/products
```
**Description:** Get products within a specific collection

**Parameters:**
- `collectionsHandle` (optional, default: 'new-balance'): Collection identifier
- `page` (optional, default: 1): Page number of results

**Response:**
```json
{
  "status": "success",
  "data": [/* Collection Products */],
  "message": null
}
```

### 6. Did You Mean (Search Suggestions)
```
GET /didumean
```
**Description:** Retrieve search term suggestions

**Parameters:**
- `searchTerm` (required): Base search term

**Response:**
```json
{
  "status": "success",
  "data": [/* Search Suggestions */],
  "message": null
}
```

### 7. Product by SKU
```
GET /products/bysku
```
**Description:** Find product details using its SKU number

**Parameters:**
- `sku` (required): Product SKU identifier

**Response:**
```json
{
  "status": "success",
  "data": {/* Product Details */},
  "message": null
}
```

### 8. All Products
```
GET /products
```
**Description:** Retrieve a paginated list of all products

**Parameters:**
- `page` (optional, default: 1): Page number
- `perPage` (optional, default: 250): Number of products per page

**Response:**
```json
{
  "status": "success",
  "data": [/* Products */],
  "message": null
}
```

### 9. Random Products
```
GET /products/random
```
**Description:** Get a selection of random products

**Parameters:** None

**Response:**
```json
{
  "status": "success",
  "data": [/* Random Products */],
  "message": null
}
```

### 10. Product URLs
```
GET /products/urls
```
**Description:** Retrieve product URLs with pagination

**Parameters:**
- `page` (optional, default: 1): Page number
- `perPage` (optional, default: 15): URLs per page

**Response:**
```json
{
  "status": "success",
  "data": [/* Product URLs */],
  "message": null
}
```

### 11. Search Product URLs
```
GET /search/products/urls
```
**Description:** Search and retrieve product URLs

**Parameters:**
- `query` (required): Search term
- `page` (optional, default: 1): Page number
- `perPage` (optional, default: 15): URLs per page

**Response:**
```json
{
  "status": "success",
  "data": [/* Matching Product URLs */],
  "message": null
}
```

## Error Handling
All endpoints return consistent error responses:
```json
{
  "status": "error",
  "message": "Detailed error description",
  "data": null
}
```

Common Error Scenarios:
- Missing required parameters
- Invalid page or pagination values
- Server-side processing errors

## Rate Limiting
*Note: Actual rate limits should be specified by your implementation*
- Recommended: 100 requests per minute
- Burst limit: 200 requests

## Recommended Use Cases
- E-commerce platforms
- Sneaker marketplace applications
- Price comparison tools
- Product recommendation systems

## Best Practices
1. Always handle pagination
2. Implement proper error handling
3. Cache results when possible
4. Use appropriate rate limiting in your application

## Example Code (Python)
```python
import requests

def search_products(query, page=1):
    url = "https://stadium-goods-api.p.rapidapi.com/products/search"
    params = {
        "query": query,
        "page": page
    }
    headers = {
        "X-RapidAPI-Key": "YOUR_API_KEY"
    }
    
    response = requests.get(url, headers=headers, params=params)
    return response.json()

# Usage
results = search_products("Nike", page=1)
```


Would you like me to elaborate on any specific section or provide more detailed information about the API?
Email us at: pintoflowpt@gmail.com
