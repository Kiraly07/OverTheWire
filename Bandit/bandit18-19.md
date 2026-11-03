# Bandit 18 → 19

## Mục tiêu

vượt `.bashrc` logout.

## Tôi thấy

SSH interactive bị logout ngay; tôi chạy lệnh trực tiếp từ máy ngoài.

## Cách làm

```bash
ssh -p 2220 bandit18@bandit.labs.overthewire.org cat readme
```

## Vì sao cách này hiệu quả

Lệnh được chạy trước khi shell interactive đọc `.bashrc`.

## Kết quả

Password của `bandit19` trong phiên đã xác minh là:

```text
KpsOfPkcP7i1FlIExk2QEjyt6dw8dxZI
```

