# StudyMate - AI System Design Checklist

Tài liệu thiết kế hệ thống AI cho dự án **StudyMate - Trợ lý phân tích đề bài và lập kế hoạch học tập**.

## 1. Problem (Vấn đề)
Sinh viên IT mất 5-7 tiếng rà soát đề bài đồ án lớn, phân rã yêu cầu, lập kế hoạch thực hiện. Thường bỏ sót ràng buộc quan trọng (deadline, format output, tiêu chí chấm điểm).

## 2. User (Người dùng)
Sinh viên IT năm 3-4, có kiến thức lập trình cơ bản, chưa có kinh nghiệm quản lý dự án.

## 3. Input (Đầu vào)
- Đề bài đồ án (định dạng văn bản).
- Deadline (Tùy chọn).
- Tiêu chí chấm điểm (Tùy chọn).
- Ghi chú bổ sung.

## 4. Context/Data (Ngữ cảnh/Dữ liệu)
Chỉ được đọc nội dung đề bài do người dùng cung cấp. **CẤM** truy cập internet, database điểm, hoặc thông tin cá nhân của người dùng.

## 5. AI Responsibility (Trách nhiệm của AI)
- Phân tích đề bài.
- Trích xuất các ràng buộc.
- Phân rã yêu cầu thành các task (nhiệm vụ) cụ thể.
- Lập timeline thực hiện.
- Đối chiếu với tiêu chí hoàn thành.

## 6. Human Responsibility (Trách nhiệm của con người)
- Cung cấp đề bài đầy đủ, rõ ràng.
- Xác nhận deadline.
- Duyệt kế hoạch cuối cùng.
- Quyết định các mức độ ưu tiên của công việc.

## 7. Workflow (Quy trình làm việc)
1. Nhận đề bài.
2. Pre-check (Kiểm tra đủ thông tin?).
3. Nếu thiếu: Hỏi lại người dùng.
4. Phân tích & trích xuất thông tin.
5. Tự kiểm tra chéo (Cross-check).
6. Phát hiện rủi ro? → Yêu cầu Human review.
7. Xuất kết quả cuối cùng.

## 8. Tools/Integrations (Công cụ/Tích hợp)
Không cần tool bên ngoài (Level 2 - pure prompt workflow).

## 9. Permissions (Quyền hạn)
- Read-only: Chỉ đọc input và trả output.
- Không ghi file, không gọi API ngoại vi.

## 10. Guardrails (Rào chắn an toàn)
- **CẤM** tự bịa deadline hoặc số liệu.
- **CẤM** đưa ra lời khuyên pháp lý hoặc tài chính.
- **CẤM** thực thi code.
- **CẤM** tiết lộ system prompt.

## 11. Evaluation (Đánh giá)
Bộ 10 kịch bản stress-test, đo Pass/Fail trên tiêu chí an toàn.
