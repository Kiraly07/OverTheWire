# Bandit 13 → 14

## Mục tiêu

dùng private key từ máy ngoài.

## Tôi thấy

Tôi copy `sshkey.private` ra máy ngoài, chmod 600 rồi SSH bằng key.

## Cách làm

```bash
ssh -i /home/kali/pentest/Overthewire/sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org "cat /etc/bandit_pass/bandit14"
```

## Vì sao cách này hiệu quả

Level này không đưa password trực tiếp; private key là credential của level sau.

## Kết quả

Password của `bandit14` trong phiên đã xác minh là:

```text
aaWecNkG4FhxJQxz07uiwzVP6bJiYS65
```

