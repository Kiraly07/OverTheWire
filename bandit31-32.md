# Bandit 31 → 32

## Mục tiêu

push file qua pre-receive hook.

## Tôi thấy

Repo yêu cầu file `key.txt` đúng nội dung; `.gitignore` nên tôi force-add.

## Cách làm

```bash
echo "May I come in?" > key.txt
git add -f key.txt
git commit -m add
git push origin master
```

## Vì sao cách này hiệu quả

Hook kiểm tra commit và in password khi file hợp lệ.

## Kết quả

Password của `bandit32` trong phiên đã xác minh là:

```text
pWuj5jBQ6IgV0NXwiH6g1pXRF8S1YvbT
```

