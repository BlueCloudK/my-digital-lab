# 🚀 Hướng Dẫn Setup Hệ Thống Quản Lý (Notion + Obsidian)

File này chứa:
1. **Prompt** để gửi cho Claude/ChatGPT giúp setup Notion tự động.
2. **Cấu trúc thư mục Obsidian** chuẩn P.A.R.A cho IT Student.
3. **Cấu trúc Database Notion** để quản lý project mạng và học tập.

---

## 1. Prompt Setup Notion (Gửi cho AI)

Copy toàn bộ đoạn code dưới đây và gửi cho Claude/ChatGPT để nó hướng dẫn bạn tạo database xịn nhất.

```markdown
Act as a Senior Notion Solutions Architect. I am an IT Student/Developer with a workflow that combines Notion (Project Management) and Obsidian (Knowledge Base).

**Goal:** Create a scalable "Master Dashboard" using the P.A.R.A method (Projects, Areas, Resources, Archives) that handles:
1. Hardware/Network Projects (e.g., Unlocking ZTE/TP-Link Routers).
2. Learning Paths (e.g., ReactJS, DevOps).
3. General/Life Tasks (e.g., Finance, Hobbies).

Please design the system with these specific requirements:

### 1. Database Philosophy
Use a **Single Master Database** approach to avoid fragmentation.

### 2. "Master Projects" Database Structure
Properties required:
* **Name:** Project Title.
* **Area (Select - The Context):**
    * Options: 🌐 Network/IoT, 💻 Coding/Dev, 🎓 University, 👤 Personal, ⚡ Others/General.
* **Type (Select - The Nature):**
    * Options:
        * 🛠️ Hands-on Lab (Technical, short-term, e.g., router hacks)
        * 📚 Learning Path (Long-term study, e.g., courses)
        * 🎓 Assignment (Hard deadline)
        * ⚡ General Task (One-off items)
* **Status (Status Property):** Not Started, In Progress, On Hold, Completed.
* **📂 Obsidian Link (URL):** Crucial property to paste the `obsidian://` URI.
* **Progress Strategy:**
    * Create a Formula property named "Visual Progress" using ASCII art (e.g., ▓▓▓▓░░░░░░).
    * Logic: Calculate % based on linked Tasks completed.
* **Priority:** High, Medium, Low.
* **Timeline:** Date Range.

### 3. "Master Tasks" Database
* **Status Property:** To-do, In Progress, 🛑 Blocked (Important for hardware projects waiting for parts), Done.
* **Relation:** Linked to "Master Projects".

### 4. Required Dashboard Views
* **View 1: "The War Room" (Network/Lab):** Board View. Filter: Area = Network/IoT. Group by Status.
* **View 2: "The Study Hall" (Learning):** Gallery View. Filter: Type = Learning Path. Show Progress Bar.
* **View 3: "The Sandbox" (General):** List View. Filter: Area = Personal OR Others.
* **View 4: "Inbox":** List View. Filter: Area is Empty (to catch uncategorized items).

### 5. Deliverables
* Step-by-step setup instructions.
* The exact Code Formula for the Visual Progress Bar.
```

## 2. Khung Cấu Trúc Obsidian (Kho Tri Thức)

```bash
📂 Obsidian Vault
├── 📂 00_Inbox                  # Nơi ghi chú nhanh, chưa kịp phân loại
│
├── 📂 10_Projects               # Dự án ĐANG chạy - Có deadline/mục tiêu
│   ├── 📁 NET_ZTE_H196A_Unlock  # Lưu lệnh Telnet, Firmware, Log Unlock
│   ├── 📁 LAB_TP_Link_EvilTwin  # Lưu code trang đăng nhập giả, config OpenWrt
│   ├── 📁 DEV_Hoc_ReactJS       # Lưu bài tập code, snippets
│   └── 📁 UNI_Bai_Tap_Lon_Java  # Lưu tài liệu đồ án trường
│
├── 📂 20_Areas                  # Trách nhiệm dài hạn - Không deadline
│   ├── 📁 Area_Network          # Lý thuyết mạng: OSI, IP, Subnetting...
│   ├── 📁 Area_Coding           # Kiến thức nền: C++, Python, Git...
│   ├── 📁 Area_University       # Ghi chép bài giảng trên lớp
│   └── 📁 Area_Personal         # Sức khỏe, Tài chính, Gym...
│
├── 📂 30_Resources              # CONTAINER cho mọi thứ linh tinh khác
│   ├── 📁 IT_Snippets           # Kho code hay dùng
│   ├── 📁 Templates             # Mẫu Note, Checklist
│   ├── 📄 Công_thuc_nau_an.md   # Ví dụ note linh tinh
│   ├── 📄 List_Phim_Hay.md
│   └── 📄 Meo_vat_cuoc_song.md
│
├── 📂 40_Archives               # Dự án đã xong - Cất đi cho gọn
│   ├── 📁 [DONE]_NET_GPON_Salvage
│   └── 📁 [DONE]_Sem1_Mathematics
│
└── 📄 00_DASHBOARD.md           # Trang chủ, chứa link đến các Project đang làm
```

## 3. Khung Cấu Trúc Notion (Trung Tâm Quản Lý)

### Database Chính: Master Projects & Learning

| Property Name   | Type     | Options / Note                                                                                             |
|-----------------|----------|------------------------------------------------------------------------------------------------------------|
| Name            | Title    | Tên dự án (VD: NET - Unlock ZTE H196A)                                                                     |
| Status          | Status   | `To-do`, `In Progress`, `On Hold`, `Done`                                                                  |
| Area (Lĩnh vực) | Select   | 🌐 `Network/IoT`, 💻 `Coding/Dev`, 🎓 `University`, 👤 `Personal`, ⚡ `Others/General`                         |
| Type (Loại hình)| Select   | 🛠️ `Hands-on Lab`, 📚 `Learning Path`, 🎓 `Assignment`, ⚡ `General Task`                                     |
| Priority        | Select   | 🔴 `High`, 🟡 `Medium`, 🔵 `Low`                                                                            |
| 📂 Obsidian Link| URL      | Dán link `obsidian://...` của folder dự án vào đây                                                         |
| Timeline        | Date     | Ngày bắt đầu -> Ngày kết thúc                                                                              |
| Progress        | Formula  | (AI sẽ viết code cho bạn)                                                                                  |
| Tasks           | Relation | Link đến database `Master Tasks`                                                                           |

### Database Phụ: Master Tasks

| Property Name  | Type     | Options / Note                                           |
|----------------|----------|----------------------------------------------------------|
| Task Name      | Title    | Việc nhỏ (VD: "Mua dây USB-TTL", "Tải Firmware")         |
| Status         | Status   | `To-do`, `In Progress`, `🛑 Blocked` (Quan trọng), `Done` |
| Parent Project | Relation | Link ngược về `Master Projects`                          |