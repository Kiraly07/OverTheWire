# Bandit 27 → 28

## Mục tiêu

đọc README trong Git repo.

## Tôi thấy

Tôi clone repo từ máy ngoài rồi đọc README.

## Cách làm

```bash
GIT_SSH_COMMAND="ssh -p 2220" git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo
cat repo/README
```

## Vì sao cách này hiệu quả

Password được để trong nội dung repo.

## Kết quả

Password của `bandit28` trong phiên đã xác minh là:

```text
y8Yd2ssKcpHpud7UvOSOxwamRMzIGIeQ
```

