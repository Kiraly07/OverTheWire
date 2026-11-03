# Bandit 19 → 20

## Mục tiêu

dùng SUID binary.

## Tôi thấy

Home có `bandit20-do`; tôi dùng nó để đọc file password level 20.

## Cách làm

```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```

## Vì sao cách này hiệu quả

SUID làm command chạy với quyền bandit20.

## Kết quả

Password của `bandit20` trong phiên đã xác minh là:

```text
4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA
```

