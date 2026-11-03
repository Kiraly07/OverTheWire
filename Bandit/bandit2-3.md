# Bandit 2 → 3

## Mục tiêu

đọc file có khoảng trắng.

## Tôi thấy

Shell tách khoảng trắng thành nhiều argument nếu không quote.

## Cách làm

```bash
cat -- "--spaces in this filename--"
```

## Vì sao cách này hiệu quả

`--` kết thúc options, còn quote giữ nguyên toàn bộ tên file.

## Kết quả

Password của `bandit3` trong phiên đã xác minh là:

```text
7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME
```

