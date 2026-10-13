# DevOps Lab 1 - CI/CD Portfolio Page

## Thông tin sinh viên
- *Họ và tên:* Ngô Quang Nghĩa
- *Mã sinh viên:* DTC235180133
- *Lớp:* KTPM K22A
- *Repository URL:* https://github.com/dtc235180133-vie/devops-lab1-portfolio
- *Link Live Website:* https://dtc235180133-vie.github.io/devops-lab1-portfolio/
---

## Báo cáo Kết quả Bài Lab

### 1. Bảng So sánh: Cách Thủ công vs Cách DevOps (CI/CD)

| Tiêu chí | Cách THỦ CÔNG (Traditional) | Cách DEVOPS (CI/CD Pipeline) |
| :--- | :--- | :--- |
| *Làm sao để deploy?* | Upload file qua FTP/SFTP hoặc copy/paste thủ công lên server. | Push code lên GitHub → pipeline tự chạy |
| *Mất bao lâu?* | Vài phút đến vài giờ. | ~10 giây |
| *Ai làm deploy?* | Con người (Developer / SysAdmin). | GitHub Actions (máy tự làm) |
| *Có bị sai sót không?* | Rất dễ sai sót (quên file, nhầm thư mục, ghi đè hỏng code). | Không — pipeline nhất quán 100% |
| *Rollback nếu lỗi?* | Tìm file cũ upload lại thủ công (tốn thời gian). | git revert + push → tự động rollback |
| *Làm sao biết deploy thành công?* | Mở web kiểm tra thủ công hoặc vào server soi log. | GitHub Actions gửi notification ✔/✖ |

---

### 2. DevOps Workflow của bài Lab
mermaid
graph LR
    PLAN["🧠 PLAN<br><b>QUYẾT ĐỊNH</b><br>Quyết định làm portfolio"] --> CODE["📝 CODE<br><b>VIẾT CODE</b><br>Viết index.html"]
    CODE --> BUILD["⚙️ BUILD<br><b>GIAI ĐOẠN BUILD</b><br>GitHub Actions chạy"]
    BUILD --> TEST["📋 TEST<br><b>KIỂM THỬ VÀ VALIDATE</b><br>Validate HTML file"]
    TEST --> DEPLOY["🚀 DEPLOY<br><b>DEPLOY LÊN PRODUCTION</b><br>GitHub Pages public"]
    DEPLOY --> MONITOR["🔔 MONITOR<br><b>THEO DÕI VÀ BÁO CÁO</b><br>Actions tab ➔ xem log"]

    style PLAN fill:#e6f7ff,stroke:#1890ff,stroke-width:2px;
    style CODE fill:#e6f7ff,stroke:#1890ff,stroke-width:2px;
    style BUILD fill:#e6f7ff,stroke:#1890ff,stroke-width:2px;
    style TEST fill:#e6f7ff,stroke:#1890ff,stroke-width:2px;
    style DEPLOY fill:#e6f7ff,stroke:#1890ff,stroke-width:2px;
    style MONITOR fill:#fffbe6,stroke:#faad14,stroke-width:2px;