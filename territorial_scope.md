# Territorial Scope — MindMesh
**Date:** 08-05-2026

## Câu hỏi 1: User EU?

* Có user EU hiện tại: Chưa có dữ liệu xác nhận cụ thể
* Kế hoạch mở rộng EU 12 tháng: NO (MVP đang tập trung vào sinh viên và nghiên cứu sinh tại Việt Nam)
* **Kết luận:** EU AI Act áp dụng = NO (ở giai đoạn hiện tại)

Tuy nhiên, có thể trong tương lai hệ thống mở public hoặc có user truy cập từ EU, đặc biệt khi dùng OpenAI API hoặc cloud infrastructure quốc tế.

---
## Câu hỏi 2: Dữ liệu Việt Nam?
### Loại dữ liệu cá nhân đang xử lý:

1. Email đăng nhập hoặc tài khoản người dùng (nếu có authentication)
2. Query tìm kiếm research / lịch sử tìm kiếm paper
3. Hành vi sử dụng sản phẩm (paper được accept/reject, click, thời gian sử dụng)
4. IP address / metadata truy cập cơ bản
5. Feedback người dùng về chất lượng summary hoặc ranking

### Có chuyển dữ liệu ra nước ngoài: 
**YES**

Lý do:
* Sử dụng OpenAI API / DeepSeek API cho summarization và reasoning

### Kết luận:
* **PDPL áp dụng = YES**
* **CTIA = Có khả năng YES nếu xử lý dữ liệu cá nhân người dùng Việt Nam và chuyển ra nước ngoài**

Hiện tại MVP chưa xử lý dữ liệu nhạy cảm cao (tài chính, sinh trắc học, y tế), nhưng vẫn có hành vi thu thập và chuyển dữ liệu người dùng thông qua API AI nước ngoài, nên cần chuẩn bị:

* Chính sách privacy rõ ràng
* User consent cơ bản
* Log dữ liệu tối thiểu
* Data retention policy đơn giản cho MVP

---
## Câu hỏi 3: Tầng rủi ro Luật AI VN?

* **Phân loại:** Trung bình
### Lập luận:
Hệ thống thuộc nhóm GenAI / AI assistant hỗ trợ tạo và tóm tắt nội dung học thuật.
Dù không hoạt động trong lĩnh vực rủi ro cao như y tế, tài chính hay tuyển dụng, sản phẩm vẫn có khả năng:

* Hallucinate thông tin học thuật
* Tóm tắt sai paper
* Làm người dùng hiểu sai nội dung research nếu không kiểm chứng nguồn

Tuy nhiên:
* Hệ thống không tự động đưa ra quyết định pháp lý/học thuật thay người dùng
* Có hiển thị citation/source
* Có cơ chế mở lại paper gốc để kiểm chứng

=> Vì vậy phù hợp với nhóm rủi ro trung bình thay vì cao.

### Nghĩa vụ tương ứng:

* Minh bạch AI-generated content
* Hiển thị source/citation rõ ràng
* Cho phép người dùng kiểm chứng thông tin
* Có cơ chế feedback/report output sai
* Không quảng bá AI như “thay thế hoàn toàn việc đọc research”

---
## 4 deadlines đã note vào Notion

* [ ] 8/5/2026 — PDPL + DTI Law hiệu lực
* [ ] 8/8/2026 — Luật AI Việt Nam hiệu lực
* [ ] 12/11/2026 — EU AI Act high-risk enforcement
* [ ] 8/7/2027 — Hết giai đoạn ân hạn đầu tiên


