# Natas 8 → 9

## Mục tiêu

Khôi phục secret từ source code.

## Tôi thấy

Source cho biết `bin2hex(strrev(base64_encode(secret)))`; tôi đảo ngược từng bước.

## Cách làm

```bash
python3 -c "import base64; e=bytes.fromhex(ENCODED); print(base64.b64decode(e[::-1]).decode())"
curl -u natas8:<password> -d "secret=<secret>&submit=1" http://natas8.natas.labs.overthewire.org/
```

## Vì sao cách này hiệu quả

Biết cả dữ liệu đã encode và hàm encode nên chỉ cần đảo ngược, không cần brute-force.

## Kết quả

Password của `natas9`:

```text
UdxmI27dTaXmnd1rxKQTfws6jihTdcQ9
```
