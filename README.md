# StudyMate — AI Study Assignment Assistant

![Level](https://img.shields.io/badge/Level-2-blue)
![Workflow Architecture](https://img.shields.io/badge/Architecture-Workflow-green)
![LLM-Agnostic](https://img.shields.io/badge/LLM-Agnostic-orange)

## 📌 Vấn đề & Giải pháp
Sinh viên IT thường gặp khó khăn và tốn nhiều thời gian (5-7 tiếng) để phân tích các đề bài đồ án lớn, dễ dẫn đến việc bỏ sót các ràng buộc quan trọng và mất điểm. 
**StudyMate** là một trợ lý AI được thiết kế để tự động phân tích đề bài, trích xuất yêu cầu, kiểm tra ràng buộc và lập kế hoạch học tập/làm bài một cách chính xác, giúp sinh viên tiết kiệm thời gian và đảm bảo chất lượng bài nộp.

## 🏗 Kiến trúc hệ thống

```text
INPUT → SANITIZE → PRE-CHECK → ANALYZE → CROSS-VALIDATE → HUMAN REVIEW → OUTPUT
                      ↓ (thiếu thông tin)
                   HỎI LẠI USER
```

## 📂 Cấu trúc thư mục

```text
studymate-ai-capstone/
├── README.md                              # Tài liệu hướng dẫn chính
├── case-study.md                          # Phân tích Case Study chuẩn Portfolio
├── LICENSE                                # MIT License
├── docs/
│   ├── system-design.md                   # Thiết kế hệ thống 11 thành phần
│   └── limitations-safety.md              # Giới hạn & khuyến cáo an toàn
├── instructions/
│   ├── system-prompt-v1.md                # System Prompt V1 (có lỗi thiết kế)
│   └── system-prompt-v2.md                # System Prompt V2 (đã tối ưu)
├── evals/
│   ├── test-cases.csv                     # 10 kịch bản kiểm thử stress-test
│   ├── v1-test-results.md                 # Kết quả kiểm thử V1
│   ├── failure-analysis.md                # Phân tích nguyên nhân gốc rễ (5-Whys)
│   ├── v1-v2-comparison.md                # Bảng đối chiếu V1 vs V2
│   └── model-swap-test.md                 # Nhật ký thử nghiệm đổi mô hình
└── demo/
    └── sample-inputs/
        ├── sample-input-01.md             # Đề bài chuẩn (Happy Path)
        └── sample-input-02.md             # Đề bài thiếu thông tin (Stress Test)
```

## 🚀 Hướng dẫn chạy nhanh (Quick Start)
1. Sao chép nội dung System Prompt V2 từ file `instructions/system-prompt-v2.md` vào ChatGPT, Claude, hoặc Gemini.
2. Paste đề bài đồ án / bài tập của bạn vào chat.
3. Nhận kết quả phân tích và kế hoạch làm bài chi tiết từ AI.

## 📊 Kết quả kiểm thử
- **Phiên bản V1:** 2/10 kịch bản đạt yêu cầu (20%)
- **Phiên bản V2:** 9/10 kịch bản đạt yêu cầu (90%)

## 🔄 Model Swap
Hệ thống đã được kiểm thử và hoạt động ổn định trên nhiều mô hình ngôn ngữ lớn khác nhau:
- GPT-4o
- Claude 3.5 Sonnet
- Gemini 1.5 Pro

## 💡 Bài học rút ra
- **Tách biệt Logic và Model:** Việc xây dựng kiến trúc không phụ thuộc vào một mô hình cụ thể giúp hệ thống linh hoạt và dễ dàng bảo trì.
- **Tầm quan trọng của Pre-check:** Kiểm tra đầu vào và yêu cầu thông tin còn thiếu trước khi phân tích giúp giảm thiểu ảo giác (hallucinations) của AI.
- **Cross-validation là bắt buộc:** Việc kiểm tra chéo các yêu cầu giúp đảm bảo AI không bỏ sót các ràng buộc quan trọng.

## ⚠️ Giới hạn đã biết
- Đôi khi AI vẫn cần sự can thiệp của con người (Human Review) đối với các đề bài có ngữ cảnh quá đặc thù hoặc mâu thuẫn.
- Phụ thuộc vào giới hạn token của từng mô hình LLM khi xử lý các đề bài quá dài.

## ✍️ Tác giả & License
- **Tác giả:** Đội ngũ phát triển
- **License:** MIT License
