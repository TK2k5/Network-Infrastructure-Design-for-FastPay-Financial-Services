# Thiết kế Hệ thống Mạng cho Công ty Tài Chính FastPay

## 1. Tổng quan dự án

Công ty tài chính **FastPay** có: - **Trụ sở chính:** Quận 1, TP.HCM\

- **2 chi nhánh:** Hà Nội và Đà Nẵng

Dịch vụ: **Thanh toán trực tuyến**, yêu cầu: - Bảo mật cao\

- Độ trễ thấp\
- Khả năng mở rộng linh hoạt\
- Kết nối ổn định giữa các chi nhánh

---

## 2. Yêu cầu hệ thống

### **2.1. Trụ sở chính -- TP.HCM**

#### 🔹 _Phân tách mạng nội bộ (Segmentation)_

- VLAN Kế toán\
- VLAN Quản lý rủi ro\
- VLAN IT\
- VLAN Server\
- VLAN Wi-Fi nhân viên\
- VLAN Wi-Fi khách (Isolated + Captive Portal)

#### 🔹 _Bảo mật nâng cao_

- Zero Trust Security Model\
- Firewall Layer 7 (NGFW)\
- IDS/IPS\
- SIEM Log Collection\
- Endpoint Security

#### 🔹 _Hybrid Cloud_

- Kết nối AWS/GCP bằng VPN hoặc Direct Connect\
- Workload: hệ thống giao dịch trực tuyến, web API, cơ sở dữ liệu dự
  phòng

---

### **2.2. Chi nhánh Hà Nội & Đà Nẵng**

- Kết nối **VPN Site-to-Site** về Data Center tại trụ sở chính\
- Giám sát hiệu suất mạng bằng công cụ mã nguồn mở:
  - Zabbix\
  - Prometheus + Grafana\
  - LibreNMS

---

## 3. Sản phẩm đầu ra

### **3.1. Sơ đồ mạng**

- **Sơ đồ mạng logic**
  - Mối quan hệ giữa các VLAN\
  - Flow truy cập giữa các bộ phận\
  - Luồng traffic giữa On-premises ↔ Cloud\
- **Sơ đồ mạng vật lý**
  - Router, Core Switch, Distribution, Access\
  - Firewalls, Load Balancers\
  - AP Wi-Fi\
- **Sơ đồ VLAN**
  - Bảng VLAN ID -- Subnet -- Department

### **3.2. Chi tiết thiết bị mạng**

Bao gồm các thiết bị dự kiến: - Router ISR/ASR\

- Switch L3 (Core), Switch L2 (Access)\
- Firewall NGFW\
- Wireless Controller + Access Point\
- Server SIEM / IDS/IPS\
- Thiết bị VPN

---

## 4. Chính sách bảo mật -- Security Policies

- Zero Trust Authentication\
- RBAC -- Role Based Access Control\
- MFA cho tất cả nhân viên\
- ACL cho từng VLAN\
- Chống tấn công:
  - DDoS Protection\
  - Port Security\
  - DHCP Snooping\
  - ARP Inspection\
  - IPS Signature-based + Behavior-based

---

## 5. Giải pháp chống tấn công mạng

- IDS/IPS inline tại DC\
- Web Application Firewall cho giao dịch trực tuyến\
- SIEM phân tích log thời gian thực\
- Backup + DR Plan trên Cloud\
- Network Access Control (NAC)\
- Monitoring continuous với Zabbix/Prometheus

---

## 6. Kế hoạch triển khai theo mô hình PDIOO

### **P -- Prepare (Chuẩn bị)**

- Thu thập yêu cầu\
- Xác định rủi ro\
- Dự toán chi phí

### **D -- Design (Thiết kế)**

- Sơ đồ logic\
- Sơ đồ vật lý\
- Bảo mật -- VLAN -- IP Plan\
- Kiến trúc Hybrid Cloud

### **I -- Implement (Triển khai)**

- Deploy thiết bị mạng\
- Cấu hình firewall, switch, routing\
- Tích hợp VPN site-to-site\
- Cấu hình cloud infrastructure

### **O -- Operate (Vận hành)**

- Giám sát 24/7\
- Alerting bằng Zabbix/Grafana\
- Vận hành hệ thống bảo mật

### **O -- Optimize (Tối ưu)**

- Tuning hiệu suất\
- Load balancing\
- Tối ưu routing và QoS\
- Kiểm thử bảo mật định kỳ

---

## 7. Đánh giá hiệu suất

- Tốc độ và độ trễ WAN\
- Tải trên firewall/switch/router\
- SLA uptime\
- Khả năng scale khi tăng số lượng người dùng\
- Báo cáo từ Zabbix / Grafana

---

## 8. Kết luận

Tài liệu này cung cấp bộ khung hoàn chỉnh cho việc xây dựng hệ thống
mạng chuyên nghiệp cho Công ty Tài Chính FastPay, đáp ứng yêu cầu: - Bảo
mật cao\

- Khả năng mở rộng\
- Tối ưu cho giao dịch trực tuyến\
- Kết nối an toàn giữa các chi nhánh
