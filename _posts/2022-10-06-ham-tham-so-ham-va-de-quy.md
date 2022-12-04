---
title: "06.Hàm, tham số hàm và đệ quy"
author_profile: true
toc: true
toc_sticky: true
excerpt: "Nói qua về cách sử dụng hàm, truyền tham số cho hàm và giới thiệu về khái niệm đệ quy trong C++."
header:
  overlay_image: ../images/postOverlay.png
  overlay_filter: 0.3
---
## 1. Khái niệm
- Là 1 đoạn chương trình giải quyết 1 vấn đề cụ thể.
- 1 hàm sẽ có tên, có thể có tham số truyền vào và giá trị trả về.
- 1 hàm có thể được gọi nhiều lần và với các đối số khác nhau (cùng kiểu dữ liệu với tham số tương ứng nếu có).
-> Có thể tái sử dụng 1 chương trình con được nhiều lần và dễ dàng trong việc sửa lỗi, nâng cấp chương trình đó.
- Chương trình sẽ thực thi các câu lệnh một cách tuần tự bên trong một hàm. Khi gặp một lời gọi hàm, CPU sẽ gián đoạn hàm hiện tại để thực thi các câu lệnh bên trong hàm được gọi. Khi hàm được gọi kết thúc, CPU sẽ lại quay lại tiếp tục thực thi hàm hiện tại.

## 2. Cú pháp
`<kiểu dữ liệu trả về> <tên hàm> (<danh sách tham số>) {`
`<khối lệnh>`
`return <giá trị trả về>;`
`}`
Hàm có thể có danh sách tham số hoặc không.

VD:
```
int Tra_ve_so(int x){
  return x;
}
```

## 3. Các loại kiểu trả về giá trị của hàm
### 3.1 Hàm có giá trị trả về
Để có 1 hàm trả về, cần phải:
- Thiết lập kiểu dữ liệu của giá trị trả về.
- Sủ dụng câu lệnh `return` để trả về 1 giá trị

> Khi gặp câu lệnh `return`, hàm sẽ trả về giá trị ngay tại thời điểm đó. Tất cả câu lệnh trong hàm, sau dòng lệnh `return` sẽ được bỏ qua. Vì vậy hàm có giá trị trả về chỉ trả về duy nhất 1 giá trị.

VD:
```
int Tra_ve_so(){
  return 6;
  return 3;
}
int main()
{
    cout << Tra_ve_so();
    return 0;
}
```
Output:

    6

### 3.2 Hàm không giá trị trả về
Hàm không có giá trị trả về sẽ có kiểu dữ liệu là `void`.
Hàm không có giá trị trả về được sử dụng khi không có mục đích tính toán.
Có thể sử dụng câu lệnh return trong hàm void để kết thúc hàm ngay lập tức.
VD:
~~~
void Spam_Hello()
{
  int i;
  do
  {
    cin >> i;
  }
  while (i >= 369);
  while (i <= 369)
  {
    cout << "Hello";
    i++;
  }
}
~~~

## 3. Truyền đối số
Là đưa các thông số cho hàm hoạt động khi bị gọi. Để làm được, cần phải nắm rõ 2 khái niệm sau:
- Tham số: là các biến được sử dụng trong một hàm mà giá trị của biến đó được cung cấp bởi lời gọi hàm. Các tham số được đặt bên trong dấu ngoặc đơn, cú pháp giống khai báo biến, cách nhau bằng dấu phẩy “,”.
- Đối số: là các giá trị truyền vào hàm qua lời gọi hàm, cách nhau bởi dấu phẩy “,”. Số lượng đối số tương ứng với số lượng tham số của hàm.

Có 2 cách truyền đối số chính.

### 3.1 Truyền tham trị
Tham số là bản sao về giá trị của đối số, đối số sẽ không thay đổi về giá trị sau khi hàm được thực thi. Từ đó hạn chế tác động không mong muốn của hàm lên đối số.
> Chú ý: truyền tham trị nên được sử dụng khi đối số là các kiểu dữ liệu đơn giản và không có nhu cầu thay đổi giá trị sau khi thực hiện hàm.

VD
```
int Tinh_Toan (int x, int y)
{
    y++;
    return x += y;
}

int main()
{
  int a = 6, b = 9;
  cout << Tinh_Toan(a, b) << endl
       << a << endl
       << b << endl;
}
```
Output:

    16
    6
    9

### 3.2 Truyền tham chiếu
- Tham số chứa địa chỉ bộ nhớ với đối số tương ứng -> nếu tham số thay đổi thì đối số sẽ thay đổi theo.
- Khi khai báo tham số, ta thêm dấu “&” sau kiểu dữ liệu của mỗi tham số.

VD
```
int Tong (int &x, int &y)
{
    return x += y;
}

int main()
{
  int a = 6, b = 9;
  cout << Tong(a, b) << endl
       << a << endl
       << b << endl;
}
```
Output:

    15
    15
    9

## 4. Đệ quy
Đệ quy là hàm có chứa lời gọi lại chính nó.
Đệ quy có 2 loại:

### 4.1 Đệ quy tuyến tính:
Hàm đệ quy tuyến tính là hàm gọi lại chính nó duy nhất 1 lần.

VD: viết hàm tính tích các số nguyên dương từ 1 đến n với n là đối số được tryền vào hàm.
```
int Tinh_Tich (int x)
{
    if (x == 1)
        return 1;
    else
        return x * Tinh_Tich(x - 1);
}
```
Giả sử ta gọi hàm `Tinh_Tich` với tham số truyền vào là x = 3.
- Ở lần gọi hàm đầu tiên, hàm sẽ trả về với giá trị là 3 * Tinh_Tich(2)
- Ở lần gọi hàm thứ 2, hàm sẽ trả về với giá trị là 3 * 2 * Tinh_Tich(1)
- Ở lần gọi hàm thứ 3, hàm sẽ trả về với giá trị là 3 * 2 * 1 = 6. Do lần gọi hàm này không còn lời gọi hàm nào nữa nên giá trị trả về cuối cùng của hàm đệ quy là 6.

### 4.2 Đệ quy nhị phân
Hàm đệ quy nhị phân là hàm gọi lại chính nó 2 lần.

VD: viết hàm xuất ra số thứ n trong dãy Fibonacci với n là đối số truyền vào hàm.
```
int fibonacci(int x) 
{
  if (x < 2) 
  {
    return x;
  } 
  else 
  {
    return fibonacci(x - 1) + fibonacci(x - 2);
  }
}
```
Giả sử ta gọi hàm `fibonacci` với tham số truyền vào là x = 3.

![Sample fibonacci binary tree](https://raw.githubusercontent.com/Ahamonuser/github/test-branches-2/Screenshot%20(2136).png)

- Ở lần gọi hàm fibonacci gốc, hàm sẽ trả về với giá trị là fibonacci(2){A} + fibonacci(1){B}. Khi đó chương trình sẽ thực hiện gọi hàm {A}.
- Ở lần gọi hàm {A}, hàm sẽ trả về với giá trị là fibonacci(1){C} + fibonacci(0){D}
- Ở lần gọi hàm {C}, hàm sẽ trả về với giá trị là 1.
- Ở lần gọi hàm {D}, hàm sẽ trả về với giá trị là 0.
- Khi đó hàm A sẽ trả về giá trị là 1 + 0 = 1 và chương trình sẽ chuyển sang gọi hàm {B}
- Ở lần gọi hàm {B}, hàm sẽ trả về giá trị là 1.
- Khi đó hàm fibonacci gốc sẽ trả về giá trị là 1 + 1 = 2 (2 chính là con số thứ 3 trong dãy fibonacci).

### 4.3 Đệ quy gián tiếp
Là hàm không gọi lại chính nó mà gọi thông qua 1 hoặc nhiều hàm khác.