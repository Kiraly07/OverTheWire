# Bandit 7 → 8

## Mục tiêu

tìm password cạnh `millionth`.

## Tôi thấy

Tôi grep đúng đầu dòng thay vì đọc file rất lớn.

## Cách làm

```bash
grep -P "^millionth\t" data.txt
```

## Vì sao cách này hiệu quả

Từ khóa là cột đầu, tab là dấu phân cách.

## Kết quả

Password của `bandit8` trong phiên đã xác minh là:

```text
VR1ljMayciFxbnUokuQmJFw6QC9VKtub
```

