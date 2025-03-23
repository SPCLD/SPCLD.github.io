1. Loại thuật toán mã hóa
Thuật toán: AES-GCM (Advanced Encryption Standard - Galois/Counter Mode)

Chiều dài khóa: 256-bit (32 byte)

Tạo khóa từ mật khẩu: Sử dụng Argon2id (một thuật toán băm mật khẩu mạnh)

2. Quá trình mã hóa (encrypt())
Bước 1: Lấy dữ liệu đầu vào (plaintext) và mật khẩu (password).

Bước 2: Tạo một iv (vector khởi tạo) ngẫu nhiên 12 byte.

Bước 3: Tạo một salt ngẫu nhiên 16 byte.

Bước 4: Băm mật khẩu bằng Argon2id để tạo khóa mã hóa AES-256.

Bước 5: Mã hóa văn bản bằng AES-GCM.

Bước 6: Gộp salt, iv, và dữ liệu đã mã hóa lại thành một mảng.

Bước 7: Mã hóa thành chuỗi Base64 để lưu trữ an toàn.

3. Quá trình giải mã (decrypt())
Bước 1: Lấy dữ liệu mã hóa (ciphertext) và mật khẩu (password).

Bước 2: Giải mã chuỗi Base64 để lấy dữ liệu nhị phân.

Bước 3: Tách salt, iv, và dữ liệu đã mã hóa.

Bước 4: Dùng salt và Argon2id để tạo khóa AES-256.

Bước 5: Giải mã bằng AES-GCM.

Bước 6: Hiển thị văn bản gốc nếu giải mã thành công.

4. Cơ chế bảo mật
Sử dụng Argon2id: Giúp bảo vệ khỏi tấn công brute-force và rainbow table.

Dùng iv riêng cho mỗi lần mã hóa: Ngăn replay attack.

AES-GCM hỗ trợ xác thực: Đảm bảo tính toàn vẹn của dữ liệu.

🛡 Kết luận: Đây là cách mã hóa AES-256-GCM mạnh mẽ với Argon2id để bảo vệ khóa, phù hợp cho bảo mật dài hạn trên web. 🚀