# Bandit 30 → 31

## Mục tiêu

tìm Git tag.

## Tôi thấy

Tôi liệt kê tag và thấy tag `secret`.

## Cách làm

```bash
git tag
git show secret
```

## Vì sao cách này hiệu quả

Tag vẫn giữ object chứa password dù file hiện tại không có.

## Kết quả

Password của `bandit31` trong phiên đã xác minh là:

```text
82NkymblpGBYmIXG6ZQ8YldBYstHpfUf
```

