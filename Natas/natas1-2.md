# Natas 1 → 2

## Mục tiêu

Đọc source dù right-click bị chặn.

## Tôi thấy

JavaScript chặn chuột phải nhưng HTML vẫn có comment chứa password.

## Cách làm

```bash
curl -u natas1:<password> http://natas1.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

Chặn context menu chỉ ảnh hưởng trình duyệt, không bảo vệ source.

## Kết quả

Password của `natas2`:

```text
vsDOxoXyq3wckCP1ZmTZ71ngIA606odB
```
