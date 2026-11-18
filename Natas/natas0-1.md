# Natas 0 → 1

## Mục tiêu

Đọc password trên trang.

## Tôi thấy

Password nằm trong HTML comment.

## Cách làm

```bash
curl -u natas0:natas0 http://natas0.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

Comment không hiện trên giao diện nhưng vẫn nằm trong response source.

## Kết quả

Password của `natas1`:

```text
scfWG6qNEIdzqVyfRwEGXyNUfFZkZeQ7
```
