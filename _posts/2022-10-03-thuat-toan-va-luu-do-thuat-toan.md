---
title: "03.Thuật toán và lưu đồ thuật toán"
author_profile: false
toc: true
toc_sticky: true
---
## 1. Khái niệm thuật toán
Là tập hợp hữu hạn các chỉ thị được định nghĩa rõ ràng để giải quyết một bài toán cụ thể.

VD: tính tổng các số từ 1 đến n với n là số nguyên dương được nhập từ bàn phím.
Khi này, chúng ta có đầu vào và đầu ra của bài toán:
- Input: số nguyên dương n thuộc N.
- Output: tổng các số từ 1 đến n.

Ta thực hiện những bước sau:
- Bước 1: khởi tạo 1 biến tổng = 0 và gán 1 biến i = 1.
- Bước 2: xét các trường hợp
  + Nếu i <= n, gán biến tổng = tổng + i, gán biến i = i + 1 và thực hiện lại bước 2.
  + Nếu i > n, kết thúc vòng lặp và xuất biến tổng.

Cấc bước thực thi trên chính là ví dụ của thuật toán.

## 2. Các tiêu chuẩn của thuật toán
- Tính chính xác: 
Quá trình tính toán hay các chỉ thị khi thực hiện là chính xác. Khi kết thúc, giải thuật phải đưa ra kết quả chính xác. 
- Tính phổ dụng: 
Có thể áp dụng cho các bài toán có đầu vào tương tự nhau. 
- Tính kết thúc: 
Thuật toán phải dừng sau một số bước nhất định.
- Tính rõ ràng: 
Các câu lệnh rõ ràng được sắp xếp theo thứ tự nhất định. 
- Tính khách quan:  
Được viết bởi nhiều người trên máy tính nhưng kết quả phải như nhau. Trong cùng một điều kiện hai bộ xử lý cùng thực hiện, thuật toán phải cho ra hai kết quả giống nhau. 

## 3. Các phương pháp biểu diễn thuật toán
- Dùng ngôn ngữ tự nhiên: 
  + Sử dụng ngôn ngữ thường ngày để liệt kê các bước của thuật toán.
  + Không yêu cầu người viết thuật toán cũng như người đọc thuật toán phải nắm các quy tắc.
  + Thường dài dòng, không thể hiện rõ cấu trúc của thuật toán, đôi lúc gây hiểu lầm, khó hiểu cho người đọc thuật toán.
  + không có một quy tắc cố định nào trong việc thể hiện thuật toán bằng ngôn ngữ tự nhiên.

VD: tính diện tích và chu vi hình tròn với bán kính r nhập từ bàn phím.

    Đầu vào: r thuộc N*.
    Đầu ra: diện tích và chu vi hình tròn bán kính r.
    Bước 1: Nhập bán kính r.
    Bước 2: Tính diện tích: Area = 2*Pi*r
            Tính chu vi: Perimeter = Pi*r*r
    Bước 3: Xuất giá trị chu vi và diện tích và kết thúc thuật toán.

- Dùng ngôn ngữ lưu đồ thuật toán:
  + Là một công cụ trực quan để diễn đạt các thuật toán.
  + Biểu diễn thuật toán bằng lưu đồ sẽ giúp người đọc theo dõi được sự phân cấp các trường hợp và quá trình xử lý của thuật toán.
  + Phương pháp lưu đồ thường được dùng trong những thuật toán có tính rắc rối, khó theo dõi được quá trình xử lý. 

![bảng các ký hiệu](https://suachuatulanh.edu.vn/wp-content/uploads/ky-hieu-luu-do-thuat-toan-1024x867-1.png)

VD: tính diện tích và chu vi hình tròn với bán kính r nhập từ bàn phim
![lưu đồ thuật toán](https://giadungnhaviet.com/wp-content/uploads/2019/08/giai-thuat-tinh-chu-vi-dien-tich.png)

hfghfg
- Dùng mã giả
  + Ngôn ngữ tựa ngôn ngữ lập trình: dùng cấu trúc chuẩn hóa, các ký hiệu toán học, biến, hàm.
  + Ưu điểm: đỡ cồng kềnh hơn lưu đồ khối.
  + Nhược điểm: không trực quan bằng lưu đồ khối.