# Natas 28 → 29

## Mục tiêu

Lấy password của `natas29` từ database jokes.

## Tôi thấy

POST `query` chuyển input thành ciphertext Base64 trong URL `/search.php/?query=`. Ciphertext có block 16 byte lặp theo cấu trúc input, cho thấy mã hóa ECB. Query SQL phía server có prefix cố định.

## Cách làm

Dùng padding để phần payload bắt đầu tại biên block, sau đó lấy các block ciphertext của payload và ghép vào ciphertext hợp lệ:

```python
payload = "' UNION SELECT password FROM users #"
# Dùng 9 ký tự padding trước payload.
# Ghép các block ciphertext bắt đầu từ block chứa payload.
```

Response trả:

```text
hwgoYUiGWoSZAqphtCAZf7u1jS16KEah
```

## Vì sao cách này hiệu quả

ECB mã hóa từng block độc lập. Có thể tái sử dụng block ciphertext của phần SQL injection trên một ciphertext khác mà không biết khóa.

## Kết quả

Password của `natas29`:

```text
hwgoYUiGWoSZAqphtCAZf7u1jS16KEah
```

