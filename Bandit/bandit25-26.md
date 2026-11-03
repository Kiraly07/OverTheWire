# Bandit 25 → 26

## Mục tiêu

thoát restricted shell.

## Tôi thấy

Login vào bandit26 mở `more`; tôi bấm `v` để vào Vim rồi mở shell Bash.

## Cách làm

```bash
ssh -i bandit26.sshkey -p 2220 bandit26@bandit.labs.overthewire.org
# more: v
# Vim: :set shell=/bin/bash
# Vim: :shell
```

## Vì sao cách này hiệu quả

Pager được chạy trong ngữ cảnh có thể gọi Vim; Vim cho phép đổi shell.

## Kết quả

Password của `bandit26` trong phiên đã xác minh là:

```text
jHdv2ELQhT22BkprMNDjybZDAkw1zeBJ
```

