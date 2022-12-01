---
title: "05.Các cấu trúc điều khiển trong C++"
author_profile: true
toc: true
toc_sticky: true
excerpt: "Giải thích về các loại cấu trúc điều khiển có trong một chương trình C++"
header:
  overlay_image: ../images/postOverlay.png
  overlay_filter: 0.3
---
Có 3 loại cấu trúc điều khiển:
- Cấu trúc tuần tự (Sequence structures) : là cách tổ chức các lệnh thành từng khối.
- Cấu trúc rẽ nhánh (Selection structures): có các cấu trúc if và switch.
- Cấu trúc lặp (Iterative structures) : có các cấu trúc for, while, do while.

![Ba loại cấu trúc điều khiển](https://ongthovuive.files.wordpress.com/2016/12/cautrucdieukhien1.png?w=584)

## 1. Cấu trúc rẽ nhánh
Cấu trúc rẽ nhánh có thể chia làm hai loại:
- Cấu trúc rẽ một trong hai nhánh: cấu trúc `if`, `if...else`, `if...else if` và lệnh `(? :)`.
- Cấu trúc rẽ một hoặc nhiều nhánh: cấu trúc `switch..case`.

### 1.1 Cấu trúc rẽ nhánh - câu lệnh điều kiện if
Cú pháp:

    if (<điều kiện>) 
      <lệnh hoặc khối lệnh>;

Nếu điều kiện là 1 biến luận lý hoặc biểu thức mang giá trị `true`, lệnh hoặc khối lệnh sẽ được thực thi, ngược lại thì không có gì xảy ra cả.
VD:
```
int x = 9;
if (x == 9)
  {
    cout << "true";
  }
```
Output:

    true

Ngược lại nếu khởi tạo biến `x` với giá trị bất kì khác 9 thì chương trình sẽ không làm gì cả.
Nên đặt các câu lệnh của câu điều kiện If bên trong cặp dấu ngoặc nhọn `{}`, dù nó chỉ có một dòng lệnh. Điều này giúp chương trình rõ ràng hơn, dễ hiểu hơn.


### 1.2 Cấu trúc rẽ nhánh - câu lệnh điều kiện if else
Cú pháp:

    if (<điều kiện>) 
      <lệnh hoặc khối lệnh X>;
    else 
      <lệnh hoặc khối lệnh Y>;

Nếu điều kiện là 1 biến luận lý hoặc biểu thức mang giá trị `true`, lệnh hoặc khối lệnh X sẽ được thực thi, ngược lại thì lệnh hoặc khối lệnh Y sẽ được thực thi.

VD:
```
int x = 6;
if (x == 3)
  {
    cout << "true";
  }
else
  {
    cout << "false";
  }
```
Output:

    false
Ngược lại nếu khởi tạo biến `x` với giá trị là 3 thì chương trình sẽ xuất ra kết quả `true`.

### 1.3 Cấu trúc rẽ nhánh - chuỗi câu lệnh điều kiện if
Được sử dung khi muốn xét nhiều hơn 2 trường hợp.
Cú pháp:

    if (<điều kiện A>)
      <lệnh hoặc khối lệnh X>;
    else if (<điều kiện B>)
      <lệnh hoặc khối lệnh Y>;
    else 
      <lệnh hoặc khối lệnh Z>;

Nếu điều kiện A là 1 biến luận lý hoặc biểu thức mang giá trị `true`, lệnh hoặc khối lệnh X sẽ được thực thi, ngược lại thì xét đến điều kiện B và thực hiện như điều kiện A.
Nếu tất cả các điều kiện trong chuỗi lệnh if đều trả về `false` thì thực hiện lệnh hoặc khối lệnh Z.

VD:
```
int x;
cin >> x;
if (x == 3)
  {
    cout << "La 3";
  }
if (x == 6)
  {
    cout << "La 6";
  }
  if (x == 9)
  {
    cout << "La 9";
  }
  else
  {
    cout << "Khong phai 3, 6 ,9";
  }
```

### 1.4 Cấu trúc rẽ nhánh switch case
Cú pháp:

    switch (<biểu thức điều kiện>) 
    {
      case <hằng số 1>:
      <khối lệnh 1>
      case <hằng số 2>:
      <khối lệnh 2>
      …
      default:
      <lệnh hoặc khối lệnh default>
    }

- Biểu thức điều kiện là một biểu thức số học nhận giá trị nguyên.
- Hằng số 1, hằng số 2,… là các hằng số kiểu số nguyên khác.
nhau, tương ứng cho các nhánh case khác nhau. Là các
hằng số mà giá trị biểu thức điều kiện có thể nhận.
- Nhánh `default` là nhánh lựa chọn mặc định khi không có nhánh nào khác được chọn. Nhánh `default` không bắt buộc phải có.
- Từ khóa `break` có thể sử dụng hoặc không. Nếu không được sử dụng thì chương trình sẽ không kết thúc cấu trúc switch case ngay khi đã thực hiện hết khối lệnh của case label có giá trị bằng với biểu thức nguyên. Thay vào đó, nó sẽ thực hiện tiếp các khối lệnh tiếp theo cho đến khi gặp từ khoá `break` hoặc dấu `}` cuối cùng của cấu trúc switch case.

VD:
```
int x;
cout << "Nhap 1 con so: ";
cin >> x;
switch (x) 
{
  case 3:
  {
    cout << "Con so vua nhap la 3."; 
    break;
  }
  case 6:
  {
    cout << "Con so vua nhap la 6."; 
    break;
  }
  case 9:
  {
    cout << "Con so vua nhap la 9."; 
    break;
  }
  default:
  cout << "Con so vua nhap khong phai la 3, 6 va 9.";
}
```

## 2. Cấu trúc lặp
- Vòng lặp phải có điểm dừng để tránh biến thành 1 vòng lặp vô hạn
- Mục đích sử dụng vòng lặp phải rõ ràng

### 2.1 Cấu trúc lặp for
Cú pháp:
```
  for (<khởi tạo biến lặp>; <điều kiện vòng lặp>; <bước nhảy>
    <lệnh hoặc khối lệnh>
```
`<khởi tạo biến lặp>:` phần này có mục đích định nghĩa và khởi tạo biến và chỉ được thực thi 1 lần duy nhất ở lần lặp đầu tiên.
`<điều kiện vòng lặp>:` phần này chứa các biểu thức điều kiện, nếu có biểu thức điều kiện đúng, các câu lệnh trong vòng lặp sẽ được thực hiện. Nếu các biểu thức điều kiện đều sai, vòng lặp sẽ kết thúc.
`<bước nhảy>:` phần này được thực thi ở cuối mỗi lần lặp. Phần này thường có mục đích tăng hoặc giảm giá trị các biến. Sau khi thực thi xong, vòng lặp quay lại phần `<điều kiện vòng lặp>`.



VD:
```
for (int i = 0; i <= 10; i++)
  cout << i;
```
Output:

    12345678910

Nếu vòng lặp `for` có nhiều biến, nhiều điều kiện dừng và có thể có nhiều biến cần cập nhật giá trị, lập trình viên có thể sử dụng toán tử phẩy `,` để tạo thêm nhiều thành phần trong mỗi phần.
> Chú ý: các biến khai báo trong phần <khởi tạo biến lặp> phải có cùng kiểu dữ liệu, cách nhau bởi dấu phẩy `,`.

VD:
```
for (int i = 5, j = 10; i < 6, j < 16; i++, j++) 
	{
		cout << i << " + " << j << " = " << (i + j) << endl;
	}
```
Output:

    5 + 10 = 15
    6 + 11 = 17
    7 + 12 = 19
    8 + 13 = 21
    9 + 14 = 23
    10 + 15 = 25

### 2.2 Cấu trúc lặp while
Cú pháp:

    while (<điều kiện vòng lặp>)
      <lệnh hoặc khối lệnh>
VD:
```
int i = 0;
while (i <= 9)
  {
    cout << i;
    i++;
  }
```
Output:

    0123456789


### 2.3 Cấu trúc lặp do-while
Cú pháp:

    do <lệnh hoặc khối lệnh>
    while (<điều kiện vòng lặp>);

VD:
```
int i = 0;
do {
  cout << i;
  i++;
}
while (i <= 9);
```
Output:

    0123456789

### 2.4 Câu lệnh break, continue
Lệnh break làm kết thúc cấu trúc lặp.
Lệnh continue bỏ qua lần lặp hiện tại.
VD:
```
int i = 0;
while (i <= 9)
  {
    if (i == 6)
      break;
    if (i == 3)
    {
      i++;
      continue;
    }
    cout << i;
    i++;
  }
```
Output:

    01245
