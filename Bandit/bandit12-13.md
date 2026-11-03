# Bandit 12 → 13

## Mục tiêu

gỡ hexdump và giải nén nhiều lớp.

## Tôi thấy

Tôi làm việc trong `/tmp`, khôi phục binary bằng `xxd`, rồi xem loại file sau mỗi lớp.

## Cách làm

```bash
mkdir -p /tmp/bandit12-work
cd /tmp/bandit12-work
cp ~/data.txt .
xxd -r data.txt data
file data
# lặp gzip/bzip2/tar theo output của file
```

## Vì sao cách này hiệu quả

Không thể chọn một lệnh giải nén duy nhất; `file` cho biết bước kế tiếp.

## Kết quả

Password của `bandit13` trong phiên đã xác minh là:

```text
qQYQiHOBPR8zR61qxYqX45quvihF2uzk
```

