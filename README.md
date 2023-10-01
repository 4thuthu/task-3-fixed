# task-3-fixed

1. Form đăng kí
   
   ![image](https://github.com/4thuthu/task-3-fixed/assets/146660348/9f4dc315-7985-43c4-93c1-c563de19d9f6)
   
   Với câu truy vấn này, ta có thể nhập username là `admin'-- ` để bỏ qua truy vấn password và đăng nhập với tư cách admin.
   Dùng hàm "mysqli_real_escape_string" để escape các kí tự ', ", \,.. ngăn người dùng chèn mã sql vào câu truy vấn.
2. Form đăng nhập

   ![image](https://github.com/4thuthu/task-3-fixed/assets/146660348/efccdb25-0f61-487e-8a6c-cac8b9afb1a3)

   Ở câu truy vấn này, kẻ tấn công có thể lợi dụng thông báo thông báo trả về để hiển thị mật khẩu của user khác bằng cách nhập username là `' union select 1 ,R_pass,1 from users where R_name = 'admin'--  `.
   ![image](https://github.com/4thuthu/task-3-fixed/assets/146660348/b3e1600f-008a-4817-bec9-5427635a7503)

  Dùng hàm MD5 để mã hóa mật khẩu dữ liệu để phòng trường hợp kẻ tấn công xem được mật khẩu. Tiếp tục dùng hàm "mysqli_real_escape_string" để ngăn việc chèn mã sql.
   

