---
title: "04.Các kiểu dữ liệu cơ sở và phép toán trong C++"
author_profile: true
toc: true
toc_sticky: true
excerpt: "Giới thiệu về các kiểu dữ liệu cơ sở như char,int,float,… và một số phép toán thông dụng trong C++."
header:
  overlay_image: ../images/postOverlay.png
  overlay_filter: 0.3
---
## 1. Kiểu số nguyên
- Có dấu: là những số nguyên dương, số nguyên âm và số 0.

| Kiểu dữ liệu | Bộ nhớ (byte) | Phạm vi giá trị                              |
| :----------- | :------------ | :------------------------------------------- |
| `char`         | 1             | -128 đến 127                                 |
| `int`          | 2             | -32768 đến 32767                             |
| `long`         | 4             | -2147483648 đến 2147483647                   |
| `long long`    | 8             | -9223372036854775808 đến 9223372036854775807 |

> Chú ý: `char` là một kiểu dữ liệu đặc biệt, nó vừa là kiểu số nguyên, cũng vừa là kiểu ký tự. Chi tiết hơn về char sẽ có ở phần kiểu ký tự, ở đây tạm coi `char` là kiểu số nguyên bình thường.

- Không dấu: là những số nguyên dương và số 0.
Số không dấu khi khai báo sử dụng từ khóa unsigned.

| Kiểu dữ liệu          | Bộ nhớ (byte) | Phạm vi giá trị                  |
| :-------------------- | :------------ | :------------------------------- |
| `unsigned char`         | 1             | 0 đến 255                        |
| `unsigned int`          | 2             | 0 đến 65535                      |
| `unsighed long`         | 4             | 0 đến 4,294,967,295              |
| `unsigned long long`    | 8             | 0 đến 18,446,744,073,709,551,615 |

## 2. Kiểu số thực

| Kiểu dữ liệu            | Bộ nhớ (byte) | Phạm vi giá trị                            |
| :---------------------- | :------------ | :----------------------------------------- |
| `float`                 | 4             | 1.17549 x 10^(-38) đến 3.40282 x 10^(38)   |
| `double`                | 8             | 2.22507 x 10^(-308) đến 1.79769 x 10^(308) |
| `long double`           | 8, 12 hoặc 16 | 3.36 x 10^(-4932) đến 1.18 x 10^(4932)     |

Ta có thể sử dụng hàm `setprecision()` thuộc thư viện `<iomanip>` để xác định số chữ số ở phần thập phân.
VD:
```
float x = 6.3333;
cout << setprecision(3) << x;
```
Output:

    6.33

## 3. Kiểu luận lý
- Dùng kiểu dữ liệu `bool`, khi khai báo sử dụng từ khóa `true`, `false` hoặc 1, 0.
- Giá trị khi được trả về của 1 biến kiểu luận lý là 1 hoặc 0.
- Có thể sử dụng `boolalpha` để xuất ra `true` hoặc `false` thay vì 1 hoặc 0 và sử dụng `noboolalpha` để quay về xuất 1 hoặc 0.

VD:
```
bool x = 6 > 9, y = 6 < 9;
cout << x << endl
     << y << endl;
cout << boolalpha;
cout << x << endl
     << y << endl;
cout << noboolalpha;
cout << x << endl
     << y << endl;
```

Output:

    0
    1
    false
    true
    0
    1

## 4. Kiểu ký tự
- Là biến dùng kiểu dữ liệu `char` để lưu 1 ký tự trong bảng mã ASCII.
- Miền giá trị: 256 ký tự trong bảng mã ASCII.
- Cũng là kiểu số nguyên do lưu mã ASCII của 1 ký tự (là 1 số nguyên). Vì vậy khi gán giá trị cho biến kiểu ký tự, có thể dùng số nguyên.
- Có thể dùng `static_cast<int16_t>(<tên biến>)` để xuất mã ASCII của ký tự lưu trong biến.
VD:
```
char x = 'A', y = 65;
cout << x << endl
     << y << endl
     << static_cast<int16_t>(x) << endl
     << static_cast<int16_t>(y);
```
Lưu ý: ký tự số nguyên không giống với mã ASCII số nguyên.

## 5. Biến
- Là tên của một vùng trong bộ nhớ RAM. Biến được dùng để nhận giá trị do người dùng nhập vào khi chạy chương trình hoặc dùng để chứa giá trị của một biểu thức
- Cú pháp khai báo:

      <kiểu dữ liệu> <tên biến>; hoặc
      <kiểu dữ liệu> <tên biến 1>, <tên biến 2>,..., <tên biến n>;
VD:
```
int a;
char b, c, d;
```

- Ngay khi được định nghĩa. biến có thể được cung cấp cho giá trị.
Cú pháp khai báo:

      <kiểu dữ liệu> <tên biến> = <giá trị biến>;

VD:
```
int a = 6;
```

## 6. Hằng
- Có giá trị không đổi trong suốt phiên chạy chương trình
- Cú pháp khai báo:

      #define <tên hằng> <giá trị> hoặc
      const <kiểu dữ liệu> <tên hằng> = <giá trị>;

VD:
```
#define Pi 3.14
const float Pi = 3.14;
```

## 7. Toán tử
- Toán tử gán: 
  + Dùng để gán giá trị cho biến
  + Cú pháp:

        <tên biến> = <giá trị>;
        <tên biến> = <tên biến>;
        <tên biến> = <biểu thức>;

Toán tử gán có thể thực hiện liên tiếp
VD:
```
int a, b, c;
a = 6;
b = c = 8;
cout << a << endl
     << b << endl
     << c;
```
Output:

    6
    8
    8

- Toán tử 1 ngôi
  + Chỉ có một toán hạng trong biểu thức.
  + Cú pháp:

        <tên biến>++; (tăng 1 đơn vị)
        <tên biến>--; (giảm 1 đơn vị)

  +  Đặt trước toán hạng
`++x` hay `--x`: thực hiện tăng/giảm trước.
  + Đặt sau toán hạng
`x++` hay `x--`: thực hiện tăng/giảm sau.

VD
```
int x = 5, y = 6, z, t;
x++;
cout << "x = " << x << endl;
z = x++;
cout << "x = " << x << endl
     << "z = " << z << endl;
y--;
cout << "y = " << y << endl;
t = --y;
cout << "y = " << y << endl
     << "t = " << t << endl;
```
Output:

    x = 6
    x = 7
    z = 6
    y = 5
    y = 4
    z = 4

- Toán tử 2 ngôi
Có hai toán hạng trong biểu thức.
`+`, `–`, `*`, `/`, `%`, `+=`, `-=`, `*=`, `/=`, `%=`.
Toán tử chia có 2 dạng:
  + Chia lấy nguyên `/`: trả về phần nguyên của phép chia.
  + Chia lấy dư `%`: trả về phần dư của phép chia

VD:
```
int x = 9, y = 3;
cout << x + y << endl
     << x - y << endl
     << x * y << endl
     << x / y << endl
     << x % y << endl;
int a = 6, b = 3;
a += b;
cout << a << endl;
a -= b;
cout << a << endl;
a *= b;
cout << a << endl;
a /= b;
cout << a << endl;
a %= b;
cout << a << endl;
```

Output:

    12
    6
    27
    3
    0
    9
    6
    18
    6
    0

- Toán tử trên bit
Tác động lên các bit của toán hạng.
`&` (and), `|` (or), `^` (xor), `~` (not), `>>` (shift right), `<<` (shift left).

| Kiểu toán tử | Ký hiệu | Ý nghĩa                              |
| :----------- | :------ | :------------------------------------------- |
| AND          | `&`     | Áp dụng toán tử luận lý AND lên từng bit     |
| OR           | `|`     | Áp dụng toán tử luận lý OR lên từng bit      |
| XOR          | `^`     | Áp dụng toán tử luận lý XOR lên từng bit     |
| NOT          | `~`     | Đảo ngược từng bit                           |
| SHIFT RIGHT  | `>>`    | Dịch các bit sang bên phải                   |
| SHIFT LEFT   | `<<`    | Dịch các bit sang bên trái                   |

VD
<!--Chưa biết kiếm ví dụ nào để giải thích đc về mấy cái bit-->

- Toán tử quan hệ
So sánh 2 biểu thức với nhau và cho ra kết quả 0 (hay false nếu sai) hoặc 1 (hay true nếu đúng).
Các toán tử: `==` , `>`, `<`, `>=`, `<=`, `!=`.
VD:
```
int x = 3, y = 9, z = 9;
cout << (x == y) << endl
     << (x < y) << endl
     << (x > y) << endl
     << (x >= y) << endl
     << (z <= y) << endl
     << (x != y) << endl;
```
Output:

    0
    1
    0
    0
    1
    1

- Toán tử luận lý
Tổ hợp nhiều biểu thức quan hệ với nhau và cho ra kết quả 0 (hay false nếu sai) hoặc 1 (hay true nếu đúng).
Các toán tử: `&&`(and), `||`(or), `!`(not)
> Chú ý: Luôn sử dụng dấu ngoặc đơn `()` khi thực hiện với các mệnh đề quan hệ để thể hiện rõ ràng ý nghĩa dòng lệnh và hạn chế sai sót.

VD:
```
int x = 3, y = 6, z = 9;
cout << ((x > y) && (x < z)) << endl
     << ((x < y) && (x < z)) << endl
     << ((x > y) || (x < z)) << endl
     << ((x > y) || (x > z)) << endl
     << (!(x < y)) << endl
     << (!(x > z)) << endl;
```
Output:

    0
    1
    1
    0
    0
    1
- Toán tử điều kiện
Đây là toán tử 3 ngôi (gồm có 3 toán hạng)
Cú pháp: 

      <biểu thức 1> ? <biểu thức 2> : <biểu thức 3>;
Nếu `<biểu thức 1>` đúng thì giá trị trả về là `<biểu thức 2>`.
Nếu `<biểu thức 1>` sai thì giá trị trả về là `<biểu thức 3`.

VD:
```
int x = 3, y = 6;
(x < y) ? cout << "true" : cout << "false";
cout << endl;
(x > y) ? cout << "true" : cout << "false";
```
Output:

    true
    false

- Toán tử phẩy
  + Các biểu thức đặt cách nhau bằng dấu `,`.
  + Các biểu thức con lần lượt được tính từ trái sang phải.
  + Biểu thức mới nhận được là giá trị của biểu thức bên phải cùng. 

VD:
```
int x = 3, y = 6, z = 9;
x = (y++, z = x + y, z += 3);
cout << x << endl
     << y << endl
     << z;
```
Output:

    13
    7
    13

- Độ ưu tiên của các toán tử
Quy tắc thực hiện:
  + Thực hiện biểu thức trong `( )` sâu nhất trước.
  + Thực hiện theo thứ tự ưu tiên các toán tử

![bảng mức độ ưu tiên các toán tử](https://i.imgur.com/eTSccce.png)