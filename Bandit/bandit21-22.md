# Bandit 21 → 22

## Mục tiêu

đọc cron job.

## Tôi thấy

Tôi xem cron config và script mà nó chạy.

## Cách làm

```bash
cat /etc/cron.d/cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

## Vì sao cách này hiệu quả

Script đã copy password bandit22 vào file `/tmp` cố định.

## Kết quả

Password của `bandit22` trong phiên đã xác minh là:

```text
RYVux2rHEm9tiXHmLFzuR7Vhx6AZQMEz
```

