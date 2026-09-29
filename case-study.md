# StudyMate — Từ Prototype lỗi đến sản phẩm đáng tin cậy

## 🔴 SITUATION (Tình huống)
Sinh viên IT thường xuyên mất từ 5-7 tiếng chỉ để đọc hiểu và phân tích các đề bài đồ án lớn. Trong quá trình này, họ thường bỏ sót các ràng buộc quan trọng dẫn đến việc mất điểm oan. Theo khảo sát, có tới 73% sinh viên cho biết họ từng nộp bài thiếu yêu cầu do không phân tích kỹ đề bài ban đầu.

## 🎯 TASK (Nhiệm vụ)
Mục tiêu là xây dựng một AI Assistant có khả năng:
- Tự động phân tích đề bài đồ án.
- Bắt buộc kiểm tra các ràng buộc (Pre-check) trước khi tiến hành lập kế hoạch.
- Kháng được các lỗi suy đoán vô căn cứ và ảo giác (hallucination) phổ biến của LLM.

## ⚙️ ACTION (Hành động)
Để giải quyết bài toán trên, tôi đã thực hiện:
- **Thiết kế kiến trúc Level 2** với cơ chế Pre-check Gate (cổng kiểm tra trước) và Cross-validation (kiểm tra chéo) để đảm bảo tính chính xác.
- **Xây dựng bộ Evals** bao gồm 10 kịch bản stress-test từ các đề thi/đồ án thực tế.
- Thông qua kiểm thử có cấu trúc, **phát hiện 8 lỗi nghiêm trọng** ở phiên bản V1.
- Áp dụng phương pháp **Root Cause Analysis (Phân tích 5-Whys)** cho 3 ca thất bại nghiêm trọng nhất (critical failures) để tìm ra nguyên nhân gốc rễ.
- **Tái thiết kế system prompt V2** dựa trên các phát hiện từ phân tích nguyên nhân gốc rễ, tập trung vào việc tạo guardrails chặt chẽ hơn.
- Thực hiện **Model Swap Test** để chứng minh kiến trúc hệ thống là model-agnostic (không phụ thuộc mô hình), hoạt động tốt trên nhiều LLM khác nhau.

## 📈 RESULT (Kết quả)
- **Tỷ lệ Pass (Thành công):** Tăng từ 2/10 PASS (20%) ở V1 lên 9/10 PASS (90%) ở V2 — cải thiện +70% độ tin cậy.
- **Tiết kiệm thời gian:** Rút ngắn ~60% thời gian đọc hiểu và phân rã bài toán cho sinh viên.
- **Tính ổn định:** Hệ thống chạy mượt mà và nhất quán trên cả 3 mô hình hàng đầu: GPT-4o, Claude 3.5, và Gemini 1.5 Pro.
- **Linh hoạt:** Kiến trúc tách biệt Logic/Model cho phép chuyển đổi giữa các mô hình trong chưa đầy 5 phút mà không làm hỏng quy trình.

## 🛠 KỸ NĂNG THỂ HIỆN
- **AI System Design:** Áp dụng checklist 11 thành phần trong thiết kế hệ thống AI.
- **LLM Evaluation & Stress Testing:** Xây dựng kịch bản kiểm thử và đánh giá chất lượng đầu ra của LLM.
- **Root Cause Analysis (5-Whys):** Phân tích và giải quyết triệt để các vấn đề của AI.
- **Model-Agnostic Architecture:** Thiết kế hệ thống không bị "khóa" (vendor lock-in) vào một nhà cung cấp LLM cụ thể.
- **Responsible AI & Safety Guardrails:** Xây dựng hàng rào bảo vệ chống lại suy đoán sai lệch của AI.

## 💡 BÀI HỌC RÚT RA
1. **Prompt Engineering không đủ, cần System Design:** Chỉ điều chỉnh prompt là không thể giải quyết triệt để lỗi của LLM; cần có các luồng kiểm tra (Pre-check, Cross-validation) ở cấp độ hệ thống.
2. **Evals là xương sống của AI Product:** Nếu không có bộ test 10 kịch bản, việc cải thiện từ V1 lên V2 chỉ là phỏng đoán mù quáng. Đánh giá có cấu trúc giúp đo lường chính xác sự tiến bộ.
3. **Fail Fast, Analyze Deep:** Việc AI đưa ra kết quả sai ở V1 là cơ hội tốt. Phân tích 5-Whys vào các ca thất bại giúp tìm ra những lỗ hổng logic mà chúng ta thường bỏ qua khi thiết kế.
4. **Model-Agnostic mang lại sự tự do:** Không phụ thuộc vào một LLM duy nhất giúp dự án an toàn hơn trước các thay đổi về giá cả, hiệu năng và tính khả dụng của các API.
