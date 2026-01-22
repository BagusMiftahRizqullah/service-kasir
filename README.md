# Kasir API

Simple REST API for a cashier system built with Go (Golang). This API manages products and categories using in-memory storage.

## Prerequisites

- Go 1.25 or higher

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd kasir-api
   ```

2. Initialize dependencies (if not already done):
   ```bash
   go mod tidy
   ```

## Running the Server

To start the API server, run:

```bash
go run main.go
```

The server will start at `http://localhost:8080`.

## API Endpoints

### Health Check
- **GET** `/health`
  - Check if the API is running.

### Products (Produk)

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/produk` | Get all products |
| POST | `/api/produk` | Create a new product |
| GET | `/api/produk/{id}` | Get a product by ID |
| PUT | `/api/produk/{id}` | Update a product |
| DELETE | `/api/produk/{id}` | Delete a product |

#### Request Body (Product)
```json
{
  "nama": "Product Name",
  "harga": 10000,
  "stok": 50
}
```

### Categories

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/categories` | Get all categories |
| POST | `/api/categories` | Create a new category |
| GET | `/api/categories/{id}` | Get a category by ID |
| PUT | `/api/categories/{id}` | Update a category |
| DELETE | `/api/categories/{id}` | Delete a category |

#### Request Body (Category)
```json
{
  "name": "Category Name",
  "description": "Category Description"
}
```

## Data Storage

Currently, this API uses in-memory storage (slices). Data will be reset when the server restarts.
