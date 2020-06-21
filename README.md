## Vai trò 
Ứng dụng có tác dụng lưu mọi dữ liệu được tạo, update vào blockchain 

## Import api to postman

url:
```
https://www.getpostman.com/collections/b18dd8f421e78873b846
```  
## Terminal1: deploy sawtooth network

```
cd network/vChain/
docker-compose up
```


## Terminal2: run application

```
cd trustion_drug_thang/
docker-compose up 
```

## Test 
1. Set biến global "app_token" trong postman 
2. Vào postman tạo tài khoản người dùng ở api tên là "CREATE_USER"
3. Chạy api tên "Authen" có vai trò như đăng nhập ở ứng dụng, với "username", "password" được tạo ở bước 2
4. Chạy api tên "company_import" và "employee_import" có vai trò như lưu thông tin company và employee ta tạo ra trong blockchain 
5. Respond ở bước 4 có trả về id có dạng "f37e7fbc-9c61-4f38-afcf-b624d54676db", nó như là id của đối tượng. Khi chạy api "get_company" và "get_employee" sửa id trong url = id của sản phẩm vừa tạo để lấy thông tin của đối tượng 
6. Chạy api tên "get_transaction" với url = id transactions của đối tượng (có thấy trong api "get_") có vai trò lấy thông tin của đối tượng từ mạng vChain đã kết nối. 
8. Chạy api tên "update_" có vài trò update đối tượng, sửa id trong phần body là id đối tượng và chỉnh sửa các thông tin cần thiết
9. Khi chạy api "get" sửa id trong url = id của đối tượng vừa tạo để lấy thông tin của đối tượng để xem phần thông tin được cập nhật 

