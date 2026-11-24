# BÀI LÀM PHA 2 

- **Họ tên:** Hồ Anh Tuấn
- **Lớp:** CNTT2
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé ra JSON

**KET QUA AI**

```text
[
{
"ma_goi": "SVT",
"ngay_su_kien": "2026-12-20",
"nguoi_lon": 2,
"tre_em": 1,
"loai_ve": "thuong",
"ghi_chu": null
},
{
"ma_goi": "FZ",
"ngay_su_kien": "2027-01-05",
"nguoi_lon": 3,
"tre_em": 0,
"loai_ve": null,
"ghi_chu": "hỗ trợ xe lăn"
},
{
"ma_goi": "VIP",
"ngay_su_kien": null,
"nguoi_lon": 4,
"tre_em": 0,
"loai_ve": "vip",
"ghi_chu": "hỗ trợ tìm chỗ cho người khiếm thị"
}
]
```

**Link trò chuyện:** https://share.gemini.google/HPSlwTMwOju7

## 4.3. Báo giá vé bằng Chain-of-Thought

**KET QUA AI**

```text
Bước 1: Tiền người lớn

Gói SVT có giá 1.200.000 đồng/người lớn, nhóm có 5 người lớn.

Phép tính: 5 × 1.200.000 = 6.000.000 đồng.

Bước 2: Tiền trẻ em

Hai trẻ 8 tuổi và 10 tuổi (từ 5 đến 11 tuổi) tính 70% giá người lớn: 70% × 1.200.000 = 840.000 đồng/trẻ.

Một bé 3 tuổi (dưới 5 tuổi) miễn phí: 0 đồng.

Phép tính: 2 × (1.200.000 × 70%) + 1 × 0 = 2 × 840.000 + 0 = 1.680.000 đồng.

Bước 3: Tiền vé

Phép tính: 6.000.000 + 1.680.000 = 7.680.000 đồng.

Bước 4: Giảm giá nhóm

Nhóm có 5 người lớn (từ 5 người lớn trở lên) nên được giảm 5% trên tiền vé.

Phép tính: 7.680.000 × 5% = 384.000 đồng (tiền vé sau giảm: 7.680.000 - 384.000 = 7.296.000 đồng).

Bước 5: Phụ thu

Có 1 người lớn chọn khu ghế ưu tiên, phụ thu 300.000 đồng/người (không giảm giá).

Phép tính: 1 × 300.000 = 300.000 đồng.

Bước 6: Tổng tiền

Phép tính: (7.680.000 - 384.000) + 300.000 = 7.296.000 + 300.000 = 7.596.000 đồng.

[RESULT: 7.596.000 đồng]
```

**Link trò chuyện:** https://share.gemini.google/XiyKXDEQuPrZ

### b) Kiểm tra kết quả AI

Đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "sai_khu_vuc",
  "so_khach": 2,
  "so_hiep_bi_anh_huong": 2,
  "tom_tat": "Khán giả gói SVT bị xếp sai khu không mái che, ghế ướt khi trời mưa trong 2 hiệp đầu."
}
```

**Link trò chuyện:** https://share.gemini.google/oekxDQvsIjRt

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**


| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| Đúng thông tin (50%) | 1.0/5.0 | Câu lỗi: "Vé Sân Vận Động bên em giá 1.000.000đ/người" và "Anh huỷ trước 3 ngày thì được hoàn tiền đầy đủ nha anh". Lý do sai: Giá chuẩn là 1.200.000đ/người lớn, huỷ >=7 ngày mới hoàn 100%, huỷ <3 ngày không hoàn. | Sửa thành: "Vé Sân Vận Động bên em giá 1.200.000đ/người lớn; huỷ từ 7 ngày hoàn 100%, 3-6 ngày hoàn 50%, dưới 3 ngày không hoàn ạ." |
| Đầy đủ 2 câu hỏi + mời cung cấp ngày & số lượng vé (30%) | 0.5/3.0 | Câu lỗi: "Anh cần gì cứ nhắn em nhé!". Lý do sai: Thiếu 2 câu hỏi cụ thể và chưa mời khách cung cấp ngày đi cũng như số lượng vé. | Sửa thành: "Anh dự định đi ngày nào và đặt bao nhiêu vé để em hỗ trợ kiểm tra và giữ chỗ cho mình ạ?" |
| Giọng điệu lịch sự không suồng sã (20%) | 1.0/2.0 | Câu lỗi: "xem rất đã luôn ạ" và "nha anh" cùng "nhé!". Lý do sai: Dùng từ ngữ suồng sã, kém trang trọng trong giao tiếp tư vấn khách hàng. | Sửa thành: "Dạ chào anh ạ, vé Sân Vận Động bên em có tầm nhìn rất đẹp, anh cần hỗ trợ thêm thông tin gì cứ cho em biết nhé." |
| Tổng điểm | 2.5/10 | Nhân viên sai giá, sai chính sách huỷ, thiếu thông tin hỏi khách và dùng từ ngữ suồng sã. | Cần rà soát lại bảng giá, chính sách hoàn huỷ và chuẩn hoá mẫu câu hỏi thông tin đặt vé. |


**Link trò chuyện:** https://share.gemini.google/qhyDDmcwVY3Q
 