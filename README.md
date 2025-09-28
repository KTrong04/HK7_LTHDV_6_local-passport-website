
# Local Passport Authentication Project

## Giới thiệu
Dự án này minh họa cách sử dụng **Express.js** và **Passport.js** để thực hiện chức năng **đăng ký, đăng nhập, hiển thị thông tin người dùng, và đăng xuất**.  
Người dùng được lưu trong **MongoDB**, và các route được bảo vệ bằng middleware `isAuthenticated`.

## Cài đặt

### 1. Clone source
```bash
git clone <repository-url>
cd <project-folder>
````

### 2. Cài dependencies

```bash
npm install
```

### 3. Chạy server

```bash
npm start
```

Mặc định server chạy tại:

```
http://localhost:3000
```

---

## Cấu trúc chính

* `routes/` : chứa các router (`register`, `login`, `profile`, `logout`)
* `models/User.js` : model của người dùng
* `views/` : các view `register.ejs`, `login.ejs`, `profile.ejs`
* `public/results/` : chứa hình test kết quả Postman

---

## Các chức năng

### 1. Register

* Route: `GET /register` và `POST /register`
* Cho phép người dùng đăng ký tài khoản mới

![Register](http://localhost:3000/results/register.png)

* Sau khi đăng ký, có thể kiểm tra dữ liệu đã lưu trong MongoDB:
  ![Show Users in MongoDB](http://localhost:3000/results/show_users_mongodb_register.png)

---

### 2. Login

* Route: `GET /login` và `POST /login`
* Xác thực người dùng qua **Passport Local Strategy**

![Login](http://localhost:3000/results/login.png)

* Sau khi login, cookie lưu trong Postman:
  ![Cookie after Login](http://localhost:3000/results/show_cookie_postman_login.png)

---

### 3. Profile (Protected Route)

* Route: `GET /profile`
* Chỉ truy cập được khi đã login

![Profile](http://localhost:3000/results/profile.png)

---

### 4. Logout

* Route: `GET /logout`
* Xoá session, redirect về trang login

![Logout](http://localhost:3000/results/logout.png)

---

## Middleware

* `isAuthenticated(req, res, next)` : bảo vệ route `/profile`

---

## Kết luận

Dự án này đã hoàn chỉnh các chức năng cơ bản:

* Đăng ký
* Đăng nhập
* Bảo vệ route
* Đăng xuất

Tất cả test case đã được chạy và lưu trong thư mục `public/results/` như yêu cầu.

```

---

Bạn muốn mình để **link dạng ảnh hiển thị luôn** (như trên) hay chỉ để **text link click vào** thôi?
```
****
