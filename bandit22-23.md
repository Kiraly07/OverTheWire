# Bandit 22 → 23

## Mục tiêu

tính tên file cron.

## Tôi thấy

Script dùng MD5 của chuỗi username để tạo tên file.

## Cách làm

```bash
cat /usr/bin/cronjob_bandit23
md5sum <<< "I am user bandit23"
cat /tmp/8ca319486bfbbc3663ea0fbe81326349
```

## Vì sao cách này hiệu quả

Tính đúng chuỗi thì tìm được file cron đã tạo.

## Kết quả

Password của `bandit23` trong phiên đã xác minh là:

```text
gKXDTAXnIz3OBxiPjRZ2uqutUlPZrBsw
```

