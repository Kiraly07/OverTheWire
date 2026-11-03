# Bandit 3 → 4

## Mục tiêu

tìm file ẩn.

## Tôi thấy

Tôi vào `inhere` rồi thấy file không hiện với `ls` thường.

## Cách làm

```bash
cd inhere
ls -la
cat ...Hiding-From-You
```

## Vì sao cách này hiệu quả

`-a` hiện dotfile; file này có tên bắt đầu bằng dấu chấm.

## Kết quả

Password của `bandit4` trong phiên đã xác minh là:

```text
xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq
```

