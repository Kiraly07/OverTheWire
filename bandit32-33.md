# Bandit 32 → 33

## Mục tiêu

thoát uppercase shell.

## Tôi thấy

Input bị đổi thành uppercase; `$0` vẫn gọi được shell hiện tại.

## Cách làm

```bash
$0
cat /etc/bandit_pass/bandit33
```

## Vì sao cách này hiệu quả

Sau `$0`, tôi có shell bình thường để đọc file password.

## Kết quả

Password của `bandit33` trong phiên đã xác minh là:

```text
u4P2CyPOwPGLe94RdD9Uo2FxFwvnFswM
```

