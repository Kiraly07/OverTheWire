# Bandit 1 → 2

## Mục tiêu

đọc file `-`.

## Tôi thấy

Tên file là dấu gạch ngang nên `cat -` sẽ bị hiểu là stdin.

## Cách làm

```bash
cat ./-
```

## Vì sao cách này hiệu quả

Prefix `./` biến nó thành một pathname bình thường.

## Kết quả

Password của `bandit2` trong phiên đã xác minh là:

```text
PK8fYLZg2hnHSz83plBL1iEPKdD3QToB
```

