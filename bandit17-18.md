# Bandit 17 → 18

## Mục tiêu

tìm dòng thay đổi.

## Tôi thấy

Hai file gần giống nhau, nên dùng diff thay vì đọc thủ công.

## Cách làm

```bash
diff -u passwords.old passwords.new
```

## Vì sao cách này hiệu quả

Dòng bắt đầu bằng `+` là dòng mới trong file mới.

## Kết quả

Password của `bandit18` trong phiên đã xác minh là:

```text
OQxXZjELndr90zuhOTDYBEomI0SZITXI
```

