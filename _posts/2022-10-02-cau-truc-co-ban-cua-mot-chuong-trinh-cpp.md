---
title: "02.Cấu trúc cơ bản của một chương trình C++"
author_profile: false
toc: true
toc_sticky: true
---
Để có thể hiểu và tự tay viết chương trình C++ điều đầu tiên cần phải biết đó là cấu trúc cơ bản của một chương trình.
Một chương trình C++ cơ bản sẽ gồm 3 thành phần sau:
- Các câu lệnh và biểu thức (Statements and expressions).
- Hàm (Functions).
- Thư viện chuẩn C++.

## 1. Câu lệnh và biểu thức
- Các câu lệnh và biểu thức là thành phần nhỏ nhất để cấu thành lên một chương trình.
- Một chương trình có thể gồm rất nhiều câu lệnh nhưng cũng có thể không có câu lệnh nào 
- Mỗi một câu lệnh sẽ yêu cầu chương trình thực hiện một nhiệm vụ nhất định.
- Câu lệnh phải kết thúc bằng dấu chấm phẩy `;`.

VD
```
include <iostream>    // khai báo thư viện iostream 
using namespace std;  // sử dụng namespace std 
int main()            // hàm main dùng để nhập code 
{
   int a = 6 ;        // khai báo biến a kiểu int và gán a = 6
   cout << a ;        // xuất màn hình giá trị a
}                     // dấu `{}` để gói các câu lệnh vào hàm main
```

Output:
6

## 2. Hàm main()
Mọi chương trình đều phải có ít nhất một hàm `main()`.
Hàm `main()` chuẩn của chúng ta sẽ có dạng:
```
int main()
{

}
```
Mặc dù không một câu lệnh, không có thư viện, chương trình vẫn chạy bình thường
Trong đó:
- `main` là tên của hàm.
- Các câu lệnh sẽ nằm trong dấu ngoặc nhọn `{ }`. Khi chương trình chạy thì những câu lệnh sẽ được thực hiện **tuần tự từ trên xuống dưới**.
- Một hàm sẽ gồm 2 thành phần đó là tên hàm và kiểu dữ liệu mà hàm trả về. Ở đây `main()` là tên hàm nên chắc chắn `int` là kiểu dữ liệu mà hàm trả về (cụ thể hơn sẽ ở bài Hàm).
- Trong một số tài liệu có thể thấy người khác viết là `void main()` nhưng cách viết `int main()` là cách viết tiêu chuẩn nhất.

## 3. Khai báo thư viện, câu lệnh xuất dữ liệu
Thư viện cơ bản chỉ là một công cụ của lập trình viên.
Ở đây mình khai báo 1 thư viện có tên là `iostream`. Thư viện này cung cấp cho chúng ta khả năng nhập, xuất dữ liệu.
Ví dụ:
```
cout << // để xuất dữ liệu
cin >>  // để nhập dữ liệu
endl    // xuống dòng
```

Thực ra thư viện `iostream` gồm rất nhiều công cụ không chỉ riêng nhập xuất. Vì vậy người tạo ra thư viện đã chia thư viện `iostream` ra thành các không gian khác nhau.
Toán tử `cout` dùng để xuất dữ liệu ra màn hình đang nằm ở một không gian nào đó mà khi chương trình chạy, nó không thể tìm ra không gian mà `cout` đang ở đó, điều này dẫn đến chương trình bị lỗi. 
Câu lệnh `using namespace std;` giúp chương trình có thể tìm được không gian cho toán tử `cout` trong thư viện `iostream`.