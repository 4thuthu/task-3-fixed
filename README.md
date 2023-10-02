# task-3-fixed

1. Form đăng nhập
   
   ![image](https://github.com/4thuthu/task-3-fixed/assets/146660348/9f4dc315-7985-43c4-93c1-c563de19d9f6)
   
   Với câu truy vấn này, ta có thể nhập username là `admin'-- ` để bỏ qua truy vấn password và đăng nhập với tư cách admin.
    Để ngăn kẻ tấn công can thiệp vào câu truy vấn, dùng Prepare Statement.
2. Form đăng kí

   ![image](https://github.com/4thuthu/task-3-fixed/assets/146660348/efccdb25-0f61-487e-8a6c-cac8b9afb1a3)

   Ở câu truy vấn này, kẻ tấn công có thể lợi dụng thông báo thông báo trả về để hiển thị mật khẩu của user khác bằng cách nhập username là `' UNION SELECT 1 ,R_pass,1 FROM users WHERE R_name = 'admin'--  `.
   ![image](https://github.com/4thuthu/task-3-fixed/assets/146660348/b3e1600f-008a-4817-bec9-5427635a7503)

  Để tránh điều này, hàm MD5 để mã hóa mật khẩu và thông báo không nên chứa dữ liệu từ Database -> xóa biến $exist_name ra khỏi thông báo. Dùng Prepare Statement để ngăn việc tiêm SQL.
3. Trang home

   ![image](https://github.com/4thuthu/task-3-fixed/assets/146660348/0ffe60b6-1202-49ea-9753-ccd29035a3bd)

   Ở trang này, có thể thay đổi cookie để làm thay đổi câu truy vấn và kiểm tra dữ liệu qua thông báo "Welcom".
   Ví dụ, khi thêm vào cookie `' and SUBSTRING((SELECT R_pass FROM users WHERE R_name = 'admin'), 1, 1) = '1`, thông báo "Welcom" vẫn được hiển thị. Bằng cách này, kẻ tấn công có thể dò ra mật khẩu của `admin`.
   Để ngăn chèn mã sql, dùng Prepare Statement để ngăn người dùng chèn mã sql.

   ![image](https://github.com/4thuthu/task-3-fixed/assets/146660348/66cac8d3-1e1d-42c2-b35e-21dd77c03511)

   


