# springboot-backend

Spring Boot backend với **Spring Data JPA** và **PostgreSQL**.

## Công nghệ

- Java 21
- Spring Boot 3.3 (Web, Data JPA, Validation)
- PostgreSQL 16
- Lombok
- Maven

## Cấu trúc

```
src/main/java/com/phanbaquang/backend
├── SpringbootBackendApplication.java
├── controller/   # REST API
├── service/      # Business logic
├── repository/   # JPA repositories
├── entity/       # JPA entities
└── exception/    # Custom exceptions
```

## Chạy dự án

1. Khởi động PostgreSQL bằng Docker:

   ```bash
   docker compose up -d
   ```

2. Chạy ứng dụng:

   ```bash
   mvn spring-boot:run
   ```

Ứng dụng chạy tại `http://localhost:8080`.

Cấu hình DB có thể ghi đè bằng biến môi trường `DB_URL`, `DB_USERNAME`, `DB_PASSWORD`.

## API mẫu

| Method | Endpoint | Mô tả |
|--------|----------|-------|
| GET | `/api/products?keyword=` | Danh sách / tìm kiếm sản phẩm |
| GET | `/api/products/{id}` | Chi tiết sản phẩm |
| POST | `/api/products` | Tạo sản phẩm |
| PUT | `/api/products/{id}` | Cập nhật sản phẩm |
| DELETE | `/api/products/{id}` | Xóa sản phẩm |

Ví dụ tạo sản phẩm:

```bash
curl -X POST http://localhost:8080/api/products \
  -H "Content-Type: application/json" \
  -d '{"name":"Laptop","description":"Gaming laptop","price":1500}'
```
