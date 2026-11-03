# Bandit 16 → 17

## Mục tiêu

tìm TLS service trong dải port.

## Tôi thấy

Tôi scan trước, sau đó thử TLS trên các port mở; port đúng là 31790.

## Cách làm

```bash
nmap -p 31000-32000 localhost -oG -
printf "%s\n" "$PASSWORD" | openssl s_client -connect localhost:31790 -quiet
```

## Vì sao cách này hiệu quả

Chỉ service đúng trả private key; dùng key đó để SSH bandit17.

## Kết quả

Password của `bandit17` trong phiên đã xác minh là:

```text
pWXMAZoxGC8JmDMfmT5MGEsobMM3vnj2
```

