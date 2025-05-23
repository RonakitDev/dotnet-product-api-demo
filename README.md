# Product API Example

## สิ่งที่ใช้

- ASP.NET Core 8
- Entity Framework Core 8 + SQLite
- Swagger UI

## คำอธิบาย

ในส่วนของฐานข้อมูลใช้ SQLite เพราะไม่ต้องติดตั้ง Database Server เพิ่มเติม ข้อมูลจะถูกเก็บในไฟล์ชื่อ `products.db`

ผมออกแบบ `Product` entity ให้รองรับ `Id`, `Name`, และ `Price` จากนั้นเชื่อมกับ `DbContext` ที่กำหนดไว้ใน `AppDbContext.cs`  
เมื่อรันโปรเจกต์ ไฟล์ฐานข้อมูลจะถูกสร้างขึ้นให้อัตโนมัติ

API endpoint รองรับฟังก์ชันพื้นฐาน ได้แก่

- `GET /products`
- `GET /products/{id}`
- `POST /products`
- `PUT /products/{id}`
- `DELETE /products/{id}`

ผมเพิ่ม Swagger UI เพื่อให้สามารถทดสอบ API ผ่านเว็บเบราว์เซอร์ได้โดยตรง

## วิธีรันโปรเจกต์

```bash
dotnet restore
dotnet ef database update
dotnet run
