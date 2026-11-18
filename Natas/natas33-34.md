# Natas 33 → 34

## Mục tiêu

Vượt kiểm tra firmware của Natas 33 để chạy PHP payload và lấy password Natas 34.

## Tôi thấy

Source tạo `Executor` mới từ request. Destructor gọi `md5_file($this->filename)`, so sánh lỏng với `$signature`, rồi chạy `php $this->filename` nếu điều kiện đúng. `filename` lấy từ POST. PHP PHAR metadata có thể tạo object `Executor` độc hại; truy cập `phar://` qua hàm file kích hoạt deserialize metadata.

## Cách làm

1. Tải `payload.php` lên, nội dung chỉ in marker và đọc `/etc/natas_webpass/natas34`:

```php
<?php
echo "NATAS33_PROBE:" . file_get_contents('/etc/natas_webpass/natas34') . ":END";
?>
```

2. Tạo PHAR với metadata `Executor` có `filename='payload.php'` và `signature=true`. Upload thành `natas33.phar`.
3. Gửi file upload bất kỳ, nhưng đặt POST `filename` thành:

```text
phar://natas33.phar/stub.txt
```

Destructor gọi `md5_file()` trên PHAR path, giải tuần tự hóa metadata; `signature=true` vượt phép so sánh lỏng và chạy `payload.php`.

## Vì sao cách này hiệu quả

`md5_file()` chấp nhận wrapper `phar://` và nạp metadata PHAR. `Executor` được tạo lại với thuộc tính đã kiểm soát. Vì kiểm tra dùng `==`, boolean `true` tương đương mọi chuỗi hash khác rỗng; destructor gọi `passthru()` chạy PHP payload đã upload.

## Kết quả

Response trả `NATAS33_PROBE:cT3LVC2sd5RtaRHdAE2xr16nYGuArbbK:END`. Đã xác thực Basic Auth thành công tại Natas 34; trang Natas 34 xác nhận: `Congratulations! You have reached the end... for now.`

