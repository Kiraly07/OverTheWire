# Natas 11 → 12

## Mục tiêu

Lấy password của `natas12` bằng cách sửa cookie XOR.

## Tôi thấy

Cookie `data` chứa JSON được XOR với một key lặp rồi Base64. Biết plaintext mặc định `showpassword=no` nên có thể suy ra key.

## Cách làm

```bash
# XOR cookie hiện tại với known plaintext để lấy repeating key
# đổi showpassword=no thành showpassword=yes rồi XOR và Base64 lại
curl -u natas11:<password> -H "Cookie: data=<forged-cookie>" http://natas11.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

XOR với key lặp không an toàn khi plaintext có cấu trúc đã biết. Khi `showpassword=yes`, server in password của level sau.

## Kết quả

Password của `natas12`:

```text
EAGkE8uzFTxeoTT2mMst9Xy7PX6guEng
```
