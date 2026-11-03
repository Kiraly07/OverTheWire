# Bandit 5 → 6

## Mục tiêu

lọc file theo thuộc tính.

## Tôi thấy

Tôi không đoán tên file; lọc theo size, không executable và text.

## Cách làm

```bash
find inhere -type f ! -executable -size 1033c | while read f; do file "$f" | grep -qi text && cat "$f"; done
```

## Vì sao cách này hiệu quả

Ba điều kiện của đề biến hàng trăm file thành một file duy nhất.

## Kết quả

Password của `bandit6` trong phiên đã xác minh là:

```text
pXa26xhMWaC2SvDotA4r9EgZkulOeSBW
```

