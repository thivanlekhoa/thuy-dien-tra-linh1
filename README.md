# Hệ Thống Quản Lý Dự Án & Gói Thầu Chuẩn Bị Vận Hành Thủy Điện Trà Linh 1 (29,6 MW)

Trang web ứng dụng độc lập (Single Page Web Application) phục vụ công tác quản lý tiến độ, hướng dẫn kỹ thuật các bước tính toán, theo dõi danh mục tài liệu yêu cầu Chủ đầu tư (Công ty TNHH Thanh Bình) cung cấp cho **Gói thầu 05 nội dung bắt buộc trước khi tích nước và phát điện thương mại**.

---

## 🚀 1. Hướng Dẫn Đưa Lên GitHub & Kích Hoạt GitHub Pages (Chạy Online Miễn Phí)

Trang web được thiết kế hoàn toàn bằng HTML5, CSS (Tailwind CDN) và Vanilla JavaScript thuần, sẵn sàng hoạt động ngay trên **GitHub Pages** mà không cần cài đặt máy chủ (Node.js hay Python backend):

### Bước 1: Tạo Repository trên GitHub và đẩy code lên
1. Truy cập [github.com](https://github.com/) và tạo một repository mới (ví dụ: `traLinh1` hoặc `tra-linh-1-pm`).
2. Mở cửa sổ dòng lệnh tại thư mục dự án và thực hiện các lệnh:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Khoi tao web quan ly du an Thuy dien Tra Linh 1"
   git branch -M main
   git remote add origin https://github.com/<tai-khoan-cua-ban>/traLinh1.git
   git push -u origin main
   ```

### Bước 2: Kích hoạt GitHub Pages
1. Trên giao diện GitHub của repository, vào mục **Settings** $\rightarrow$ chọn mục **Pages** (ở menu cột bên trái).
2. Tại mục **Build and deployment**:
   - **Source**: Chọn `Deploy from a branch`.
   - **Branch**: Chọn nhánh `main` và thư mục `/ (root)`.
3. Nhấn **Save**.

### Bước 3: Truy cập trang web online
Sau khoảng 1 - 2 phút, GitHub sẽ cấp cho bạn một đường link online công khai, có dạng:
👉 `https://<tai-khoan-cua-ban>.github.io/traLinh1/`

Bạn có thể gửi link này cho đồng nghiệp, lãnh đạo hoặc Chủ đầu tư xem trên bất kỳ thiết bị nào (máy tính, máy tính bảng, điện thoại).

---

## 💻 2. Hướng Dẫn Sử Dụng Offline Trực Tiếp Trên Máy Tính
Nếu chưa đưa lên GitHub, bạn chỉ cần:
- Nhấp đúp chuột trực tiếp vào tệp [`index.html`](file:///G:/My%20Drive/.FAWARE/2026/traLinh1/index.html) để mở trên trình duyệt (Chrome, Edge, Firefox, Cốc Cốc, Safari...).
- Toàn bộ tính năng tương tác, tính toán và lưu trữ dữ liệu đều hoạt động mượt mà.

---

## 🛠️ 3. Các Phân Hệ Chức Năng Chính Trong Web App

### 1. Dashboard Điều Hành
- Thống kê tỷ lệ hoàn thành tiến độ tổng thể, đếm ngược mốc 60 ngày, theo dõi ngân sách 510 triệu VNĐ sau VAT.
- Thanh tiến độ động theo thời gian thực cho từng hạng mục trong 5 gói việc.
- Cảnh báo đường găng kỹ thuật (Critical Path): mối quan hệ phụ thuộc giữa Bản đồ ngập lụt $\rightarrow$ Phương án EAP, số liệu lòng dẫn $\rightarrow$ HEC-RAS...

### 2. Thông Số Kỹ Thuật Nền Tảng Dự Án (Sau Hiệu Chỉnh 2026)
- Bảng thông số kỹ thuật chuẩn hóa theo Văn bản thẩm định số **5535/SCT-QLNL** ngày 11/9/2026 của Sở Công Thương TP Đà Nẵng:
  - Công suất lắp máy $N_{lm} = 29,6\text{ MW}$ (2 tổ máy tuabin Pelton trục đứng).
  - Cột nước $H_{tt} = 416\text{ m}$, lưu lượng $Q_{max} = 8,27\text{ m}^3\text{/s}$, điện lượng $E_0 = 93,465\text{ tr.kWh/năm}$.
  - Hồ chứa: MNDBT $1.167\text{m}$, MNC $1.150\text{m}$, $V_{tb} = 1,271\text{ tr.m}^3$, $V_{hi} = 0,873\text{ tr.m}^3$.
  - Cụm đầu mối: Đập tràn tự do $B=40\text{m}$, cống xả cát $4\times 5\text{m}$, ống xả dòng chảy tối thiểu D250 ($Q_{tt} \ge 0,246\text{ m}^3\text{/s}$).
- Bảng phân tích so sánh trước & sau điều chỉnh thiết kế cơ sở:
  - **Bỏ tháp điều áp**: Phân tích an toàn nước va do tuabin Pelton kéo dài thời gian đóng mở $T=35\text{s}$, giải quyết xung đột GPMB đất nghĩa trang.
  - **Bỏ đập phụ và Chiron 3**: Giảm chiếm dụng đất rừng >10%, tiết kiệm chi phí xây dựng.
  - **Cải tạo tuyến hầm Chiron 4**: Chuyển thành hầm ngầm đấu nối trực tiếp vào hầm chính.

### 3. Hướng Dẫn Kỹ Thuật, Bước Tính Toán & Dữ Liệu Từng Hạng Mục
Chi tiết phương pháp luận, công thức, phần mềm áp dụng cho từng hạng mục:
1. **Lập bản đồ ngập lụt hạ du đập** (66 tr - 45 ngày): Mô hình HEC-RAS / MIKE FLOOD mô phỏng 4 kịch bản xả lũ $P=1\%$, kiểm tra $P=0,2\%$, bất thường và vỡ đập giả định.
2. **Phương án ứng phó tình huống khẩn cấp - EAP** (60 tr - 15 ngày): Ma trận cảnh báo, bản đồ sơ tán dân xã Trà Linh, Trà Tập, hậu cần "4 tại chỗ".
3. **Quy trình vận hành hồ chứa thủy điện** (90 tr - 30 ngày): Cân bằng nước, cắt giảm lũ, xả tối thiểu theo Giấy phép 308/GP-BNNMT, vận hành liên hồ Trà Linh 2.
4. **Phương án cắm mốc phạm vi bảo vệ đập** (144 tr - 30 ngày): Quy chuẩn đập cấp II (Điều 23 NĐ 114/2018), hệ tọa độ VN-2000, quy cách mốc M200.
5. **Phương án cắm mốc hành lang bảo vệ nguồn nước hồ chứa** (150 tr - 30 ngày): Nghị định 53/2024/NĐ-CP, đường viền MNDBT 1.167m, dự toán cắm mốc.

### 4. Danh Mục Hồ Sơ & Dữ Liệu CĐT (Check-list Tương Tác)
- Bảng check-list 15 hồ sơ/số liệu yêu cầu CĐT cung cấp.
- Cho phép nhấp trực tiếp vào nút trạng thái để chuyển đổi: `Chưa nhận` $\rightarrow$ `Đang xử lý` $\rightarrow$ `Đã nhận`.
- Hệ thống tự động ghi nhớ và tính toán tỷ lệ % tài liệu đã thu thập được.

### 5. Quản Lý Công Việc & Phân Công Đồng Nghiệp (WBS)
- Danh mục hơn 25 đầu việc phân rã chi tiết cho toàn bộ 5 gói việc.
- Cho phép phân công người phụ trách (Kỹ sư Thủy lực, Trắc địa, Thủy năng, Dự toán...).
- Lọc theo gói thầu, lọc theo trạng thái (Chưa làm, Đang làm, Chờ thẩm tra, Hoàn thành).
- Nút **"Thêm công việc"** cho phép tạo thêm nhiệm vụ mới linh hoạt.

### 6. Tiến Độ 60 Ngày (Gantt Chart Trực Quan)
- Sơ đồ Gantt phân kỳ 8 tuần công tác thực hiện gối đầu và song song.
- Làm rõ các mốc nghiệm thu kỹ thuật và bàn giao thẩm định.

---

## 🔄 4. Cơ Chế Lưu Trữ & Chia Sẻ Dữ Liệu Cập Nhật Giữa Các Đồng Nghiệp
1. **Tự động lưu (LocalStorage)**: Mọi thao tác tick chọn hoàn thành task, đổi trạng thái hồ sơ, thêm việc mới đều được tự động lưu trên trình duyệt của người dùng.
2. **Xuất file JSON (Export)**: Khi bạn cập nhật xong tiến độ, bấm nút **"Xuất JSON"** ở góc trên bên phải để tải file `TraLinh1_PM_State_YYYY-MM-DD.json`.
3. **Nhập file JSON (Import)**: Gửi file này qua Zalo/Email cho đồng nghiệp. Đồng nghiệp chỉ cần mở web và bấm **"Nhập JSON"** để cập nhật dữ liệu đồng bộ ngay lập tức.
4. **In báo cáo (Print / Save PDF)**: Bấm nút **"In Báo cáo"** để xuất ra bản in hoặc lưu thành file PDF báo cáo định kỳ nộp Ban Giám đốc hoặc Chủ đầu tư.

---

## 📁 5. Danh Mục Tệp Kèm Theo Trong Thư Mục Dự Án
- [`index.html`](file:///G:/My%20Drive/.FAWARE/2026/traLinh1/index.html): Trang web ứng dụng hoàn chỉnh.
- [`Ke_Hoach_Va_Yeu_Cau_Cung_Cap_So_Lieu_TL1.docx`](file:///G:/My%20Drive/.FAWARE/2026/traLinh1/Ke_Hoach_Va_Yeu_Cau_Cung_Cap_So_Lieu_TL1.docx): File Word công văn quy chuẩn gửi Chủ đầu tư.
- [`Danh_Muc_Yeu_Cau_So_Lieu_TL1.xlsx`](file:///G:/My%20Drive/.FAWARE/2026/traLinh1/Danh_Muc_Yeu_Cau_So_Lieu_TL1.xlsx): Bảng tính Excel danh mục số liệu và phân công thực hiện.
