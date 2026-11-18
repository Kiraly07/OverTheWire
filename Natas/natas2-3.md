# Natas 2 → 3

## Mục tiêu

Tìm file public trong webroot.

## Tôi thấy

HTML/source gợi ý thư mục `/files`; users.txt chứa password.

## Cách làm

```bash
curl -u natas2:<password> http://natas2.natas.labs.overthewire.org/files/users.txt
```

## Vì sao cách này hiệu quả

File được đặt dưới webroot và không có lớp kiểm soát riêng.

## Kết quả

Password của `natas3`:

```text
K30JrSRHzjxq3paUQuwozY4MNvmNFyhI
```
