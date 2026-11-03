# Bandit 4 → 5

## Mục tiêu

tìm file readable.

## Tôi thấy

Có nhiều file `-fileXX`, nhưng chỉ một file là ASCII text.

## Cách làm

```bash
file inhere/*
cat inhere/-file07
```

## Vì sao cách này hiệu quả

`file` phân biệt dữ liệu binary với file text.

## Kết quả

Password của `bandit5` trong phiên đã xác minh là:

```text
6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG
```

