# Bandit 6 → 7

## Mục tiêu

tìm file trên toàn hệ thống.

## Tôi thấy

File không nằm trong home, nên tôi tìm từ `/` theo owner, group và size.

## Cách làm

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null -exec cat {} \;
```

## Vì sao cách này hiệu quả

`2>/dev/null` bỏ lỗi permission; các predicate khớp đúng mô tả.

## Kết quả

Password của `bandit7` trong phiên đã xác minh là:

```text
Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3
```

