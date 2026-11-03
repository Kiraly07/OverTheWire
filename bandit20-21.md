# Bandit 20 → 21

## Mục tiêu

kiểm tra password qua daemon.

## Tôi thấy

Tôi mở listener trả password hiện tại, rồi chạy `suconnect`.

## Cách làm

```bash
printf "%s\n" "$PASSWORD" | nc -l -p 12345 &
./suconnect 12345
```

## Vì sao cách này hiệu quả

Binary đọc một dòng từ listener; nếu đúng nó gửi password level sau.

## Kết quả

Password của `bandit21` trong phiên đã xác minh là:

```text
bW9kBv5WC3P4yoDyf12LSdGuNz5ka6hY
```

