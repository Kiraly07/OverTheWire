# Natas 30 → 31

## Mục tiêu

Vượt đăng nhập Perl để lấy password Natas 31.

## Tôi thấy

Source ghép SQL trực tiếp qua `DBI->quote(param('username'))` và `DBI->quote(param('password'))`. `CGI::param()` với giá trị lặp có thể trả danh sách; DBI quote nhận thêm đối số tùy chọn cho kiểu dữ liệu.

## Cách làm

Gửi POST có username `natas30`, password gồm hai giá trị `0 OR 1=1` và `4`:

```python
requests.post(
    'http://natas30.natas.labs.overthewire.org/index.pl',
    auth=('natas30', '<password hiện tại>'),
    data=[('username', 'natas30'), ('password', '0 OR 1=1'), ('password', '4')]
)
```

Response trả `win!` và password Natas 31.

## Vì sao cách này hiệu quả

Danh sách tham số lặp khiến `param('password')` cung cấp đối số bổ sung cho `quote()`; giá trị thứ hai `4` được DBI diễn giải như cờ `SQL_INTEGER`, nên giá trị đầu không được quote như chuỗi. Điều kiện `0 OR 1=1` làm query trả một row.

## Kết quả

Response thành công trả password `aQzrirxwd2Wiaoq8HnSjcc8IUWlxdd1z`. Đã xác thực Basic Auth thành công tại Natas 31.

