# Bandit 26 → 27

## Mục tiêu

chạy SUID sau khi escape.

## Tôi thấy

Sau khi có Bash từ level trước, tôi chạy binary SUID trong home.

## Cách làm

```bash
./bandit27-do cat /etc/bandit_pass/bandit27
```

## Vì sao cách này hiệu quả

Binary đọc file với quyền bandit27.

## Kết quả

Password của `bandit27` trong phiên đã xác minh là:

```text
STJLJBRRphMxKB392CT4iOr5CbzPU9ER
```

