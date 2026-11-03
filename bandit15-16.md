# Bandit 15 → 16

## Mục tiêu

gửi password qua TLS.

## Tôi thấy

Netcat thường không đủ vì port 30001 yêu cầu TLS.

## Cách làm

```bash
cat /etc/bandit_pass/bandit15 | openssl s_client -connect localhost:30001 -quiet
```

## Vì sao cách này hiệu quả

`openssl s_client` tạo kết nối TLS rồi truyền stdin.

## Kết quả

Password của `bandit16` trong phiên đã xác minh là:

```text
kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V
```

