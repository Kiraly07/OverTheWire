# Bandit 9 → 10

## Mục tiêu

tìm chuỗi readable trong binary.

## Tôi thấy

`cat` cho output rác; tôi lấy các chuỗi ASCII rồi lọc dấu `=`.

## Cách làm

```bash
strings data.txt | grep -E "=+"
```

## Vì sao cách này hiệu quả

Password nằm trong một chuỗi readable có nhiều dấu bằng.

## Kết quả

Password của `bandit10` trong phiên đã xác minh là:

```text
B0s2khmbT9u0geKuOoVGW3JZKhndE3BG
```

