# Bandit 8 → 9

## Mục tiêu

tìm dòng xuất hiện một lần.

## Tôi thấy

`uniq` chỉ so sánh các dòng liền nhau nên phải sort trước.

## Cách làm

```bash
sort data.txt | uniq -u
```

## Vì sao cách này hiệu quả

`-u` chỉ giữ dòng có đúng một lần xuất hiện.

## Kết quả

Password của `bandit9` trong phiên đã xác minh là:

```text
EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl
```

