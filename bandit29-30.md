# Bandit 29 → 30

## Mục tiêu

tìm branch khác.

## Tôi thấy

Branch master không có password; tôi liệt kê remote branch rồi xem `origin/dev`.

## Cách làm

```bash
git branch -a
git show origin/dev:README.md
```

## Vì sao cách này hiệu quả

Thông tin nhạy cảm nằm ở branch phụ, không phải working tree hiện tại.

## Kết quả

Password của `bandit30` trong phiên đã xác minh là:

```text
jq9Dfg2rXsfYsWMgFuKlXhphjdH7USgX
```

