# Bandit 14 → 15

## Mục tiêu

gửi password qua TCP.

## Tôi thấy

Tôi gửi password hiện tại đến localhost port 30000.

## Cách làm

```bash
cat /etc/bandit_pass/bandit14 | nc localhost 30000
```

## Vì sao cách này hiệu quả

Service chỉ trả password mới khi input đúng.

## Kết quả

Password của `bandit15` trong phiên đã xác minh là:

```text
pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7
```

