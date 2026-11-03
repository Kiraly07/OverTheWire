# Bandit 11 → 12

## Mục tiêu

giải ROT13.

## Tôi thấy

Tôi thử bảng chữ cái xoay 13 vị trí theo đề.

## Cách làm

```bash
tr "A-Za-z" "N-ZA-Mn-za-m" < data.txt
```

## Vì sao cách này hiệu quả

`tr` thay từng chữ theo bảng ROT13; số và ký tự khác giữ nguyên.

## Kết quả

Password của `bandit12` trong phiên đã xác minh là:

```text
GROozWPO8QyN0mGrjUkID0WCYkZiQxrN
```

