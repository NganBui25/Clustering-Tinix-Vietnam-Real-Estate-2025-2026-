# Dự Án Cuối Kỳ (CK) - Khoa Học Dữ Liệu
# Dự Án Phân Cụm Dữ Liệu Bất Động Sản Việt Nam (2025-2026)

Kho lưu trữ này chứa toàn bộ mã nguồn, dữ liệu và báo cáo phân tích được phát triển cho bài toán phân tích và phân cụm bộ dữ liệu **Tinix Vietnam Real Estate Listings (2025-2026)**. Mục tiêu của dự án là khám phá các mẫu tiềm ẩn trong dữ liệu và nhóm các bất động sản thành các phân khúc có ý nghĩa nghiệp vụ (ví dụ: chung cư cao cấp, nhà phố thương mại, đất nền ngoại ô, v.v.).

---

## 📌 Tổng quan dự án (Overview)

Dự án được thực hiện theo quy trình chuẩn của một bài toán phân tích và học máy không giám sát (Unsupervised Learning), bao gồm các giai đoạn chính:

* **Khám phá & Tiền xử lý dữ liệu (EDA & Data Preprocessing):** * Xử lý các giá trị bị thiếu (Missing values) và làm sạch dữ liệu nhiễu (Outliers) đối với các cột quan trọng như `price`, `area`.
    * Kỹ thuật đặc trưng (Feature Engineering): Tạo thêm các thuộc tính mới như đơn giá trên mét vuông (`price_per_sqm`).
    * Mã hóa các biến phân loại (Encoding) và Chuẩn hóa dữ liệu số (Scaling).
* **Lựa chọn & Huấn luyện mô hình (Model Selection & Training):** * Áp dụng các thuật toán phân cụm phù hợp với dữ liệu lớn (như K-Means, MiniBatchKMeans).
    * Xác định số lượng cụm (K) tối ưu bằng phương pháp Elbow Method.
* **Đánh giá mô hình & Phân tích cụm (Model Evaluation & Profiling):** * Đo lường hiệu suất phân cụm thông qua các chỉ số như Silhouette Score và Davies-Bouldin Index.
    * Phân tích đặc trưng phổ biến (Mean, Median, Mode) của từng cụm để tiến hành gán nhãn nghiệp vụ (Business Labeling) cho các phân khúc bất động sản.

---

## 📌 Cấu trúc thư mục (Repository Structure)

```text
├── data/               # Thư mục chứa dữ liệu 
│   ├── raw/            # Dữ liệu gốc tải từ Hugging Face
│   └── processed/      # Dữ liệu đã qua làm sạch và tiền xử lý
├── notebooks/          # Chứa các file Jupyter Notebook (.ipynb)
│   ├── 01_EDA_and_Cleaning.ipynb     # Khám phá và làm sạch dữ liệu
│   └── 02_Clustering_Modeling.ipynb  # Huấn luyện mô hình và đánh giá
├── reports/            # Chứa các tài liệu, báo cáo cuối kỳ và biểu đồ
├── .gitignore          # File cấu hình bỏ qua các tệp không cần thiết khi push lên Git
├── requirements.txt    # Danh sách các thư viện Python cần thiết (pandas, scikit-learn, v.v.)
└── README.md           # Tài liệu hướng dẫn dự án (File này)