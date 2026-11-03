# Bandit 28 → 29

## Mục tiêu

xem Git history.

## Tôi thấy

README hiện tại che password; tôi xem commit cũ.

## Cách làm

```bash
git log --all --oneline
git show HEAD~1
```

## Vì sao cách này hiệu quả

Secret bị xóa ở commit mới nhưng vẫn còn trong history.

## Kết quả

Password của `bandit29` trong phiên đã xác minh là:

```text
Em7eGtqaMySwNFjCpwzzHhLhospOcdt0
```

