# Thiết kế Hệ thống Mạng cho Công ty Tài Chính FastPay

## 1. Tổng quan dự án

Công ty tài chính **FastPay** có:

- **Trụ sở chính:** Quận 1, TP.HCM

- **2 chi nhánh:** Hà Nội và Đà Nẵng

Dịch vụ: **Thanh toán trực tuyến**, yêu cầu:

- Bảo mật cao
- Độ trễ thấp
- Khả năng mở rộng linh hoạt
- Kết nối ổn định giữa các chi nhánh

---

## 2. Yêu cầu hệ thống

### **2.1. Trụ sở chính -- TP.HCM**

#### 🔹 _Phân tách mạng nội bộ (Segmentation)_

- VLAN Kế toán
- VLAN Quản lý rủi ro
- VLAN IT
- VLAN Server
- VLAN Wi-Fi nhân viên
- VLAN Wi-Fi khách

---

### **2.2. Chi nhánh Hà Nội & Đà Nẵng**

- Kết nối **VPN Site-to-Site** về Data Center tại trụ sở chính

---
